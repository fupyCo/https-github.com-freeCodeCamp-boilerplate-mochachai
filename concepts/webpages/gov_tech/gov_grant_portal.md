# Government Grant Funding Portal Template

## Overview

This is a professional government website template designed for grant funding services. The template follows government web design best practices inspired by the Canada.ca design system, featuring clean layouts, accessibility features, and professional styling.

## Design Principles

### Color Scheme
- **Primary Blue**: `#26374a` - Used for headers, buttons, and primary elements
- **Accent Red**: `#af3c43` - Used for borders and highlights
- **Text**: `#333` - Dark grey for optimal readability
- **Background**: `#f5f5f5` - Light grey for page background
- **White**: `#fff` - For content cards and header

### Typography
- **Headings**: Lato (bold, professional)
- **Body Text**: Noto Sans (clean, readable)
- **Font Sizes**: Responsive and accessible

## Key Features

### 1. Header Section
- **Logo Placement**: Top-left corner with government branding
- **Language Toggle**: Bilingual support (EN/FR) in top bar
- **Search Functionality**: Prominent search bar for finding grants
- **User Information**: Displays logged-in user with avatar
- **Skip to Content Link**: Accessibility feature for keyboard navigation

### 2. Alert Banner
- **Customizable Alerts**: Warning and emergency alert styles
- **Icon Support**: Visual indicators for alert types
- **Prominent Placement**: Immediately visible below header

### 3. Navigation
- **Breadcrumb Trail**: Shows user location in site hierarchy
- **Clear Structure**: Easy navigation back to previous pages

### 4. Service Categories
- **Grid Layout**: 6 main service categories
- **Icon Placeholders**: Ready for custom icons/images
- **Hover Effects**: Interactive feedback on mouse-over
- **Accessible Links**: Full card is clickable

Categories include:
- Business Grants
- Research & Development
- Community Programs
- Education & Training
- Environmental Initiatives
- Arts & Culture

### 5. Featured Content
- **Featured Programs Section**: Highlights important updates
- **Image Placeholders**: Ready for featured images (180px height)
- **Call-to-Action Links**: Encourages user engagement
- **Responsive Grid**: Adapts to different screen sizes

### 6. Most Requested Services
- **Quick Links**: Fast access to common tasks
- **6 Essential Services**:
  - Apply for a Grant
  - Check Application Status
  - Check Eligibility
  - Application Guidelines
  - Important Deadlines
  - Contact Support

### 7. Footer
- **Four Column Layout**: Organized link categories
- **Sections**:
  - Services
  - Resources
  - About
  - Legal
- **Government Branding**: Logo and copyright
- **Last Updated Date**: Transparency feature

## Responsive Design

The template is fully responsive with breakpoints at:
- **Desktop**: 1200px max-width container
- **Tablet**: Adjusts grid layouts
- **Mobile**: 768px breakpoint - stacks elements vertically

### Mobile Optimizations
- Header elements stack vertically
- Single column layouts for cards
- Touch-friendly button sizes
- Optimized navigation

## Accessibility Features

### WCAG 2.1 Compliance
- **Skip to Main Content**: Keyboard navigation support
- **Semantic HTML**: Proper heading hierarchy
- **ARIA Labels**: Screen reader support
- **Focus Indicators**: Visible keyboard focus (3px solid outline)
- **Color Contrast**: Meets AA standards
- **Alt Text Ready**: Image placeholders marked for descriptions

### Keyboard Navigation
- All interactive elements are keyboard accessible
- Tab order follows logical flow
- Focus states clearly visible

## Image Placeholders

The template includes placeholders for:
1. **Government Logo**: 80x80px in header and 60x60px in footer
2. **Service Icons**: 120px height in service cards
3. **Featured Images**: 180px height in featured content
4. **User Avatar**: 35px circular avatar

Replace placeholders with actual images:
```html
<!-- Replace this -->
<div class="service-icon">[Image: Business Icon]</div>

<!-- With this -->
<div class="service-icon">
  <img src="/images/business-icon.png" alt="Business services">
</div>
```

## Interactive Features

### Search Functionality
The search form is ready for backend integration:
```javascript
// Add form submission handler
document.querySelector('.search-form').addEventListener('submit', function(e) {
    e.preventDefault();
    const query = document.querySelector('.search-input').value;
    // Implement search logic here
});
```

### Language Toggle
Currently shows an alert. Implement full bilingual support:
```javascript
function toggleLanguage() {
    // Load French or English version
    // Update page content
    // Save preference
}
```

### User Authentication
The user info section displays logged-in user:
```html
<div class="user-info">
    <div class="user-avatar">JD</div>
    <span>John Doe</span>
</div>
```

Integrate with your authentication system to show actual user data.

## Customization Guide

### Changing Colors
Update the CSS variables or replace color values:
```css
/* Primary color */
#26374a → Your color

/* Accent color */
#af3c43 → Your color
```

### Adding New Service Categories
Copy the service card structure:
```html
<a href="/your-service" class="service-card">
    <div class="service-icon">[Your Icon]</div>
    <h3>Your Service Title</h3>
    <p>Your service description...</p>
</a>
```

### Modifying Alert Types
Two alert styles are included:
- **Warning** (default): Yellow background
- **Emergency**: Red background

```html
<!-- Emergency alert -->
<div class="alert-banner emergency">
    <!-- Alert content -->
</div>
```

## Integration Points

### Backend Integration
1. **User Authentication**: Connect user-info section to auth system
2. **Search**: Implement search API endpoint
3. **Application Forms**: Link to application submission system
4. **Status Tracking**: Connect to application database
5. **Content Management**: Dynamic loading of featured content

### Database Schema Suggestions
```
grants
- id
- title
- category
- description
- deadline
- amount
- eligibility

applications
- id
- user_id
- grant_id
- status
- submitted_date
- documents
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## File Structure

```
gov_tech/
├── gov_grant_portal.html    # Main template file
└── gov_grant_portal.md       # This documentation
```

## Future Enhancements

Consider adding:
1. **Application Dashboard**: User-specific grant tracking
2. **Document Upload**: Secure file upload system
3. **Email Notifications**: Deadline reminders
4. **Advanced Search**: Filters by category, amount, deadline
5. **Progress Indicators**: Multi-step application forms
6. **Analytics**: Track user behavior and popular grants
7. **Chatbot**: AI-powered support assistant
8. **Calendar Integration**: Sync deadlines to user calendar

## Best Practices

### Content
- Use clear, concise language
- Avoid jargon
- Provide examples
- Include contact information
- Keep information up-to-date

### Performance
- Optimize images (use WebP format)
- Minify CSS and JavaScript
- Use CDN for fonts
- Implement lazy loading for images
- Enable caching

### Security
- Implement HTTPS
- Sanitize user inputs
- Use CSRF tokens
- Secure session management
- Regular security audits

## Credits

Design inspired by:
- Canada.ca Design System
- Government of Canada Web Standards
- WCAG 2.1 Accessibility Guidelines

## License

This template is provided as-is for government and public sector use. Modify as needed for your specific requirements.

## Support

For questions or issues with this template:
1. Review this documentation
2. Check accessibility compliance
3. Test on multiple browsers
4. Validate HTML/CSS
5. Review government web standards

## Version History

- **v1.0** (November 2024): Initial release
  - Complete government grant portal template
  - Responsive design
  - Accessibility features
  - Service categories
  - Featured content sections
  - Professional styling

---

**Last Updated**: November 23, 2024
