# Quick Start Guide: Admin Access

## 🔐 Admin Access Control Summary

The College Sports Society website has **strict admin access control** to ensure only authorized users can manage content.

## ✅ Who Can Access the Admin Panel?

### Admin Users Only
- Users with `role: 'admin'` in their profile
- First registered user automatically becomes admin
- Other users must be promoted by an existing admin

### Regular Users Cannot Access
- Users with `role: 'user'` cannot access `/admin`
- Attempting to access will redirect to "Access Denied" page
- Admin link is hidden from non-admin users

## 🚀 Getting Started as Admin

### Step 1: Become an Admin
**Option A: Be the First User**
1. Register a new account (if no users exist yet)
2. You automatically become admin
3. Login and access `/admin`

**Option B: Get Promoted by Existing Admin**
1. Register a regular account
2. Ask an existing admin to promote you
3. Admin goes to: Admin Panel → Users tab → Edit your profile → Change role to "admin"
4. Logout and login again to see changes

### Step 2: Access Admin Panel
1. Login with your admin account
2. Look for the "Admin" link in the navigation menu (with shield icon 🛡️)
3. Click to access the admin panel
4. Or navigate directly to `/admin`

### Step 3: Manage Content
Use the tabbed interface to manage:
- **Tournaments**: Add/edit/delete sports tournaments
- **Results**: Manage match results and scores
- **Medals**: Update medal table and rankings
- **Gallery**: Upload/manage event photos and videos
- **FAQs**: Add/edit frequently asked questions
- **Announcements**: Post important announcements
- **Users**: View and manage registered users
- **Inquiries**: Respond to contact form submissions

## 🔒 Security Features

### Multi-Layer Protection
✅ **Database Level**: Row Level Security (RLS) policies
✅ **Route Level**: Protected routes with role checking
✅ **UI Level**: Admin controls hidden from non-admins
✅ **API Level**: All operations verify admin status

### What Happens When Non-Admin Tries to Access?
1. User navigates to `/admin`
2. System checks if user is logged in
   - If not logged in → Redirect to `/login`
   - If logged in → Check role
3. System checks if user is admin
   - If admin → Grant access ✅
   - If not admin → Redirect to `/access-denied` ❌

## 👤 Checking Your Role

### Method 1: Profile Page
1. Login to your account
2. Go to Profile page
3. Look for the role badge (top-right of profile card)
   - Blue badge = Admin
   - Gray badge = User

### Method 2: Navigation Menu
1. Login to your account
2. Check the navigation menu
   - If you see "Admin" link with shield icon → You're admin
   - If you don't see it → You're a regular user

## 🛠️ Admin Operations

### All Admin Features Support CRUD
- ✅ **Create**: Add new content
- ✅ **Read**: View all content
- ✅ **Update**: Edit existing content
- ✅ **Delete**: Remove content (with confirmation)

### Special Features
- **Gallery**: Automatic image compression (max 1MB)
- **Users**: Promote users to admin role
- **Inquiries**: Mark as read/responded
- **Announcements**: Toggle active/inactive status

## ❓ Common Questions

### Q: I'm the first user but can't access admin panel
**A:** Try these steps:
1. Logout completely
2. Clear browser cache
3. Login again
4. Check your profile page for role badge
5. If still not admin, check database: `SELECT role FROM profiles WHERE id = 'your-id'`

### Q: Can I have multiple admins?
**A:** Yes! Admins can promote other users to admin status via the Users Management tab.

### Q: Can I demote an admin to regular user?
**A:** Yes, admins can change any user's role (including other admins) in the Users Management tab.

### Q: What if I accidentally demote all admins?
**A:** You'll need database access to manually update a user's role back to 'admin':
```sql
UPDATE profiles SET role = 'admin' WHERE id = 'user-id';
```

### Q: Can regular users see admin content?
**A:** Regular users can view public content (tournaments, gallery, FAQs) but cannot access the admin panel or perform any CRUD operations.

## 📋 Admin Checklist

Before starting, ensure:
- [ ] You have an admin account
- [ ] You can see the "Admin" link in navigation
- [ ] Your profile shows "admin" role badge
- [ ] You can access `/admin` without being redirected

## 🎯 Quick Access

### Admin Panel URL
```
https://your-domain.com/admin
```

### Admin Navigation
```
Header → Admin (shield icon) → Admin Panel
```

### Admin Tabs
1. Tournaments
2. Results
3. Medals
4. Gallery
5. FAQs
6. Announcements
7. Users
8. Inquiries

## 📞 Need Help?

If you're having trouble accessing the admin panel:
1. Check your role in Profile page
2. Try logging out and back in
3. Clear browser cache and cookies
4. Contact technical support
5. Check the detailed documentation in `ADMIN_ACCESS_CONTROL.md`

## 🎉 You're Ready!

Once you have admin access, you have full control over all website content. Use the admin panel responsibly and keep your credentials secure.

---

**Remember**: Only authorized admin users can access the admin panel. This ensures the security and integrity of your website content.
