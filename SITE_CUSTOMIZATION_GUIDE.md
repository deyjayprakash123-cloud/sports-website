# Site Customization Guide

## Overview
This guide explains how to customize the College Sports Society website's appearance, content, and social media links through the Admin Panel.

## Table of Contents
1. [Site Settings Management](#site-settings-management)
2. [Hero Slides Management](#hero-slides-management)
3. [Social Media Integration](#social-media-integration)
4. [Contact Information](#contact-information)

---

## Site Settings Management

### Accessing Site Settings
1. Log in as an admin user
2. Navigate to **Admin Panel** (`/admin`)
3. Click on the **Settings** tab

### Available Settings

#### Contact Information
Manage how users can reach you:

- **Contact Email**: Primary email address for inquiries
  - Example: `sports@outr.ac.in`
  - Displayed on contact page and footer

- **Contact Phone**: Phone number for direct contact
  - Example: `+91-1234567890`
  - Displayed on contact page

- **Address**: Physical location of the sports society
  - Example: `Odisha University of Technology and Research, Bhubaneswar, Odisha`
  - Displayed on contact page and footer

#### Social Media Links
Connect your social media profiles:

- **Facebook URL**: Link to your Facebook page
  - Example: `https://facebook.com/yourpage`
  
- **Twitter URL**: Link to your Twitter profile
  - Example: `https://twitter.com/yourhandle`
  
- **Instagram URL**: Link to your Instagram account
  - Example: `https://instagram.com/youraccount`
  
- **YouTube URL**: Link to your YouTube channel
  - Example: `https://youtube.com/@yourchannel`
  
- **LinkedIn URL**: Link to your LinkedIn page
  - Example: `https://linkedin.com/company/yourcompany`

**Note**: Social media icons will only appear in the footer if you provide valid URLs (not the default placeholder URLs).

#### General Settings
Basic site information:

- **Site Name**: Name of your organization
  - Example: `College Sports Society`
  - Displayed in footer and page titles

- **Site Tagline**: Main tagline for your site
  - Example: `Unleash Your Spirit`
  - Can be used in hero sections

### How to Update Settings
1. Navigate to **Settings** tab in Admin Panel
2. Find the setting you want to update
3. Edit the value in the input field
4. Click the **Save** button (💾 icon) next to the field
5. You'll see a success notification when saved

---

## Hero Slides Management

### What are Hero Slides?
Hero slides are the large, prominent banners on the home page that showcase your main messages and calls-to-action. They can be configured as a carousel with multiple slides.

### Accessing Hero Slides
1. Log in as an admin user
2. Navigate to **Admin Panel** (`/admin`)
3. Click on the **Hero Slides** tab

### Creating a New Hero Slide

1. Click the **Add Slide** button
2. Fill in the following fields:

#### Required Fields
- **Title**: Main headline text
  - Example: `UNLEASH YOUR SPIRIT`
  - Displayed in large, bold text

#### Optional Fields
- **Subtitle**: Supporting text below the title
  - Example: `JOIN THE LEGACY. COMPETE. CONQUER. BELONG.`
  - Displayed in smaller text with accent color

- **Primary Button Text**: Text for the main call-to-action button
  - Example: `REGISTER NOW`
  
- **Primary Button Link**: Where the primary button leads
  - Example: `/register`
  - Can be internal (`/page`) or external (`https://example.com`)

- **Secondary Button Text**: Text for the secondary button
  - Example: `EXPLORE EVENTS`
  
- **Secondary Button Link**: Where the secondary button leads
  - Example: `/tournaments`

- **Background Image URL**: URL to a custom background image
  - Leave empty to use the default gradient background
  - Recommended size: 1920x1080px or larger

- **Display Order**: Number determining slide order
  - Lower numbers appear first
  - Example: 1, 2, 3, etc.

- **Active**: Toggle to show/hide the slide
  - Only active slides appear on the home page

3. Click **Create** to save the slide

### Editing a Hero Slide
1. Find the slide you want to edit
2. Click the **pencil icon** (✏️) on the slide card
3. Update the fields as needed
4. Click **Update** to save changes

### Activating/Deactivating a Slide
- Click the **toggle switch** on the slide card
- Inactive slides won't appear on the home page but remain saved

### Deleting a Hero Slide
1. Click the **trash icon** (🗑️) on the slide card
2. Confirm the deletion in the dialog
3. The slide will be permanently removed

### Best Practices for Hero Slides

#### Content Guidelines
- **Keep titles short and impactful**: 3-5 words maximum
- **Make subtitles descriptive**: Explain your value proposition
- **Use action-oriented button text**: "Register Now", "Join Today", "Learn More"
- **Ensure links are valid**: Test all button links before activating

#### Visual Guidelines
- **Use high-quality images**: Minimum 1920x1080px resolution
- **Ensure text readability**: Dark backgrounds work best with light text
- **Maintain consistency**: Use similar styling across all slides
- **Limit slide count**: 3-5 slides maximum for best user experience

#### Technical Guidelines
- **Set proper display order**: Organize slides logically
- **Test on mobile**: Ensure slides look good on all screen sizes
- **Optimize images**: Compress images to improve loading speed
- **Use internal links when possible**: Better for SEO and user experience

---

## Social Media Integration

### How Social Media Links Work

#### Footer Display
- Social media icons appear in the website footer
- Only icons with valid URLs are displayed
- Default placeholder URLs (like `https://facebook.com`) are hidden
- Icons are styled with your site's accent colors

#### Supported Platforms
1. **Facebook** - Blue circular icon
2. **Twitter** - Light blue circular icon
3. **Instagram** - Gradient circular icon
4. **YouTube** - Red circular icon
5. **LinkedIn** - Professional blue circular icon

### Setting Up Social Media Links

1. Go to **Admin Panel** → **Settings** tab
2. Scroll to the **Social Media Links** section
3. For each platform you use:
   - Enter the complete URL to your profile/page
   - Click the Save button
   - Verify the icon appears in the footer

### Example URLs
```
Facebook:  https://facebook.com/outr.sports
Twitter:   https://twitter.com/outr_sports
Instagram: https://instagram.com/outr_sports
YouTube:   https://youtube.com/@outrsports
LinkedIn:  https://linkedin.com/company/outr-sports
```

### Removing Social Media Links
- To remove a social media icon from the footer:
  1. Clear the URL field for that platform
  2. Or set it back to the default placeholder URL
  3. Save the changes

---

## Contact Information

### Where Contact Info Appears
- **Contact Page**: Full contact details with form
- **Footer**: Email and address
- **About Page**: Organization information

### Updating Contact Information

1. Navigate to **Admin Panel** → **Settings**
2. Find the **Contact Information** section
3. Update the following fields:

#### Email Address
- Used for the contact form
- Displayed on the contact page
- Format: `email@domain.com`

#### Phone Number
- Displayed on the contact page
- Format: `+91-XXXXXXXXXX` or your local format
- Include country code for international visibility

#### Physical Address
- Full address of your organization
- Can include multiple lines
- Example:
  ```
  Odisha University of Technology and Research
  Bhubaneswar, Odisha 751003
  India
  ```

4. Click **Save** after each update

### Best Practices

#### Email
- Use a professional email address
- Ensure the email is monitored regularly
- Consider using a dedicated sports society email

#### Phone
- Include country code for international users
- Verify the number is correct and active
- Consider adding office hours information

#### Address
- Provide complete, accurate address
- Include postal code
- Add landmarks if helpful for visitors

---

## Tips for Effective Customization

### Branding Consistency
- Use consistent colors across all content
- Maintain the same tone in all text
- Keep logo and imagery style uniform

### Content Strategy
- Update hero slides seasonally or for major events
- Keep social media links current
- Review contact information quarterly

### User Experience
- Test all links after updating
- Ensure mobile responsiveness
- Keep loading times fast by optimizing images

### Maintenance Schedule
- **Weekly**: Check for outdated announcements
- **Monthly**: Review hero slides relevance
- **Quarterly**: Verify contact information
- **Annually**: Update social media strategies

---

## Troubleshooting

### Social Media Icons Not Showing
- **Issue**: Icons don't appear in footer
- **Solution**: 
  1. Verify URLs are complete (include `https://`)
  2. Ensure URLs are not default placeholders
  3. Clear browser cache and refresh

### Hero Slide Not Displaying
- **Issue**: Slide doesn't appear on home page
- **Solution**:
  1. Check if slide is marked as "Active"
  2. Verify display order is set correctly
  3. Ensure title field is not empty

### Settings Not Saving
- **Issue**: Changes don't persist after saving
- **Solution**:
  1. Verify you're logged in as admin
  2. Check internet connection
  3. Try refreshing the page and saving again
  4. Check browser console for errors

### Button Links Not Working
- **Issue**: Hero slide buttons don't navigate correctly
- **Solution**:
  1. Verify link format (internal: `/page`, external: `https://...`)
  2. Test links in a new tab first
  3. Ensure no typos in URLs

---

## Advanced Customization

### Custom Background Images
For hero slides with custom backgrounds:

1. **Prepare Your Image**:
   - Minimum size: 1920x1080px
   - Format: JPG or PNG
   - Optimize for web (compress to < 500KB)

2. **Upload Image**:
   - Use the Gallery Manager to upload
   - Copy the image URL
   - Paste into "Background Image URL" field

3. **Best Practices**:
   - Use dark images for better text contrast
   - Ensure important content isn't obscured
   - Test on multiple screen sizes

### Multiple Call-to-Action Buttons
- Primary button: Main action (e.g., Register)
- Secondary button: Alternative action (e.g., Learn More)
- Both are optional but recommended for engagement

### Slide Timing
- Slides auto-rotate every 5 seconds
- Users can manually navigate with arrows
- Pause on hover (automatic)

---

## Support

### Getting Help
If you encounter issues:
1. Check this guide first
2. Review the main documentation
3. Contact technical support
4. Check the admin panel for error messages

### Reporting Issues
When reporting problems, include:
- What you were trying to do
- What happened instead
- Screenshots if applicable
- Browser and device information

---

## Changelog

### Version 1.2.0
- Added Site Settings management
- Added Hero Slides management
- Added Social Media integration
- Added Contact Information management
- Improved admin panel organization

---

**Last Updated**: 2025-12-02  
**Version**: 1.2.0  
**Maintained By**: Development Team
