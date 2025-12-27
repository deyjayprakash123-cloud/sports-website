# Admin Access Control Documentation

## Overview
The College Sports Society website implements a robust role-based access control system to ensure that **only authorized admin users** can access the admin panel and perform administrative operations.

## Access Control Levels

### 1. Public Access (No Authentication Required)
- Home page
- Tournaments page (view only)
- Gallery page (view only)
- FAQs page (view only)
- Contact page (form submission)
- Login page
- Register page

### 2. Authenticated User Access (Login Required)
- Profile page (view and edit own profile)
- All public pages

### 3. Admin Access (Admin Role Required)
- Admin panel (`/admin`)
- All CRUD operations on:
  - Tournaments
  - Results
  - Medal Table
  - Gallery
  - FAQs
  - Announcements
  - User Management
  - Inquiries

## How Admin Access Works

### Role Assignment
1. **First User Becomes Admin**: The first user to register automatically receives the `admin` role
2. **Admin Promotion**: Existing admins can promote other users to admin status via the Users Management tab
3. **Role Storage**: User roles are stored in the `profiles` table in the database

### Authentication Flow
```
User attempts to access /admin
    ↓
Is user logged in?
    ├─ No → Redirect to /login
    └─ Yes → Check user role
              ├─ Role = 'admin' → Grant access to admin panel
              └─ Role = 'user' → Redirect to /access-denied
```

## Technical Implementation

### 1. Database Level (Row Level Security)
```sql
-- RLS policies ensure only admins can modify data
CREATE POLICY "Admins have full access" ON profiles
  FOR ALL TO authenticated USING (is_admin(auth.uid()));

-- Helper function to check admin status
CREATE OR REPLACE FUNCTION is_admin(uid uuid)
RETURNS boolean LANGUAGE sql SECURITY DEFINER AS $$
  SELECT EXISTS (
    SELECT 1 FROM profiles p
    WHERE p.id = uid AND p.role = 'admin'
  );
$$;
```

### 2. Application Level (React Components)

#### AuthContext (`@/contexts/AuthContext.tsx`)
Provides authentication state and admin status:
```typescript
interface AuthContextType {
  user: User | null;
  profile: Profile | null;
  loading: boolean;
  isAdmin: boolean;  // Computed from profile.role === 'admin'
  refreshProfile: () => Promise<void>;
}
```

#### ProtectedRoute Component (`@/components/ProtectedRoute.tsx`)
Guards routes that require authentication or admin access:
```typescript
<ProtectedRoute requireAdmin>
  <Admin />
</ProtectedRoute>
```

**Logic:**
1. Shows loading skeleton while checking authentication
2. Redirects to `/login` if user is not authenticated
3. Redirects to `/access-denied` if admin access is required but user is not admin
4. Renders protected content if all checks pass

#### Route Configuration (`@/routes.tsx`)
Admin route is protected:
```typescript
{
  name: 'Admin',
  path: '/admin',
  element: (
    <ProtectedRoute requireAdmin>
      <Admin />
    </ProtectedRoute>
  ),
  adminOnly: true,
}
```

### 3. UI Level (Header Component)

#### Admin Link Visibility
The admin link in the navigation menu is only visible to admin users:
```typescript
{isAdmin && (
  <Link to="/admin">
    <Shield className="w-4 h-4" />
    <span>Admin</span>
  </Link>
)}
```

This applies to both:
- Desktop navigation
- Mobile menu

## Access Denied Page

When a non-admin user attempts to access the admin panel, they are redirected to `/access-denied` which displays:
- Clear explanation of why access was denied
- Information about admin privileges
- Navigation options to go back or return home

## Security Features

### 1. Multi-Layer Protection
- **Database Layer**: RLS policies prevent unauthorized data modifications
- **API Layer**: All admin operations check user permissions
- **Route Layer**: Protected routes block unauthorized access
- **UI Layer**: Admin controls are hidden from non-admin users

### 2. Session Management
- User authentication state is managed by Supabase Auth
- Profile data (including role) is fetched on login
- Auth state persists across page refreshes
- Automatic logout on session expiration

### 3. Real-time Role Updates
- When an admin changes a user's role, the change is immediate
- Users must refresh or re-login to see role changes reflected
- `refreshProfile()` function can be called to update profile data

## Testing Admin Access Control

### Test Case 1: Non-Admin User
1. Register a new account (not the first user)
2. Login with the new account
3. Attempt to navigate to `/admin`
4. **Expected**: Redirected to `/access-denied`
5. **Expected**: No "Admin" link visible in navigation

### Test Case 2: Admin User
1. Login with the first registered account (auto-admin)
2. Navigate to `/admin`
3. **Expected**: Admin panel loads successfully
4. **Expected**: "Admin" link visible in navigation
5. **Expected**: All CRUD operations work

### Test Case 3: Role Promotion
1. Login as admin
2. Go to Admin Panel → Users tab
3. Edit a regular user and change role to "admin"
4. **Expected**: User's role updates successfully
5. Have that user logout and login again
6. **Expected**: User now has admin access

### Test Case 4: Unauthenticated Access
1. Logout (or use incognito mode)
2. Attempt to navigate to `/admin`
3. **Expected**: Redirected to `/login`

## Admin Operations Security

### Create Operations
- Only admins can create new content
- All create operations check `isAdmin` status
- Database RLS policies enforce admin-only inserts

### Read Operations
- Public users can read most content (tournaments, gallery, FAQs)
- Admins can read all data including user profiles and inquiries

### Update Operations
- Only admins can update content
- Users can only update their own profile (except role field)
- Database RLS policies prevent unauthorized updates

### Delete Operations
- Only admins can delete content
- All delete operations require confirmation
- Database RLS policies enforce admin-only deletes

## Troubleshooting

### Issue: User is admin but can't access admin panel
**Solution:**
1. Check if user's role in database is 'admin'
2. Try logging out and logging back in
3. Clear browser cache and cookies
4. Check browser console for errors

### Issue: Admin link not showing
**Solution:**
1. Verify user role in database: `SELECT role FROM profiles WHERE id = 'user-id'`
2. Check AuthContext is providing correct `isAdmin` value
3. Ensure profile data is loaded (not null)

### Issue: Access denied even though user is admin
**Solution:**
1. Verify database RLS policies are correctly configured
2. Check if `is_admin()` function exists and works
3. Ensure user is authenticated (not just logged in locally)

## Best Practices

### For Administrators
1. **Limit Admin Accounts**: Only promote trusted users to admin
2. **Regular Audits**: Periodically review admin user list
3. **Secure Credentials**: Use strong passwords for admin accounts
4. **Activity Monitoring**: Monitor admin actions through database logs

### For Developers
1. **Never Bypass Security**: Don't add backdoors or skip auth checks
2. **Test Thoroughly**: Test all access control scenarios
3. **Keep Updated**: Regularly update Supabase and dependencies
4. **Log Security Events**: Log admin actions for audit trail

## API Endpoints Security

All admin operations use Supabase client with RLS:
```typescript
// Example: Only admins can delete tournaments
export const deleteTournament = async (id: string) => {
  const { error } = await supabase
    .from('tournaments')
    .delete()
    .eq('id', id);
  // RLS policy ensures only admins can execute this
  if (error) throw error;
};
```

## Summary

The admin access control system ensures that:
✅ Only authenticated users with `role: 'admin'` can access the admin panel
✅ Non-admin users are redirected with a clear explanation
✅ Admin links are hidden from non-admin users
✅ Database-level security prevents unauthorized data modifications
✅ Multiple layers of protection ensure robust security
✅ First registered user automatically becomes admin
✅ Admins can promote other users to admin status

This multi-layered approach provides comprehensive security while maintaining a good user experience.
