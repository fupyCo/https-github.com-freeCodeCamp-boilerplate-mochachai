# iOS Widgets - Blank Template

## Overview

This is a blank, customizable template for iOS widgets that can be adapted to any project. It includes all four main iOS widget types with clean, minimalist design following Apple's Human Interface Guidelines. Use this as a starting point for your own app's widgets.

## What's Included

### 1. Lock Screen Widget
- Small widget for iPhone lock screen
- Displays app logo, title, content, and details
- Customizable colors and content

### 2. Home Screen Widget
- Medium-sized widget (2x2 grid)
- Shows app logo, widget title, and status items
- Three status rows with customizable badges
- Last updated timestamp

### 3. Notification Banner
- Standard iOS notification pop-up
- App icon, name, and timestamp
- Notification title and message
- Two interactive buttons (Dismiss/View)
- Glassmorphism design

### 4. Live Activity
- Dynamic Island compatible
- Real-time progress tracking
- Progress bar with percentage
- Two action buttons
- Dark mode optimized

### 5. Phone Mockup
- Complete iPhone lock screen preview
- Shows notification and widgets in context
- Realistic device design with notch

## Quick Start Guide

### Step 1: Replace Branding

**Logo Placeholders** - Replace `APP` text:
```html
<!-- Find this -->
<div class="lockscreen-logo">APP</div>

<!-- Replace with image or your text -->
<div class="lockscreen-logo">
    <img src="your-logo.png" alt="Logo">
</div>
<!-- OR -->
<div class="lockscreen-logo">YA</div>
```

**App Name** - Replace "Your App Name":
```html
<!-- Find this -->
<div class="lockscreen-title">Your App Name</div>

<!-- Replace with -->
<div class="lockscreen-title">My App</div>
```

### Step 2: Customize Colors

**Primary Brand Color** - Update the gradient:
```css
/* Find these gradients and replace with your brand colors */
background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);

/* Example: Red to orange gradient */
background: linear-gradient(135deg, #ef4444 0%, #f97316 100%);

/* Example: Green gradient */
background: linear-gradient(135deg, #10b981 0%, #059669 100%);
```

**Status Badge Colors** - Customize the badge styles:
```css
.status-badge.primary {
    background: #your-light-color;
    color: #your-dark-color;
}
```

### Step 3: Update Content

**Lock Screen Widget**:
```html
<div class="lockscreen-content">Your Main Text</div>
<div class="lockscreen-detail">Your detail text</div>
```

**Home Screen Status Items**:
```html
<div class="status-row">
    <span class="status-label">Your Label</span>
    <span class="status-badge primary">Your Status</span>
</div>
```

**Notification Content**:
```html
<div class="notification-title">Your Notification Title</div>
<div class="notification-message">Your notification message here.</div>
```

**Live Activity**:
```html
<div class="live-activity-title">Your App Name</div>
<div class="live-activity-status">Your Current Status</div>
<div class="live-activity-detail">Step X of Y • Time info</div>
```

### Step 4: Customize Button Actions

Replace the alert() functions with your app's deep links:
```javascript
function viewNotification() {
    // Replace with your app's deep link
    window.location.href = 'yourapp://notification/view';
}
```

## Customization Options

### Color Schemes

**Professional Blue** (Default):
```css
Primary: #6366f1 to #8b5cf6
Background: #1e293b
```

**Business Green**:
```css
Primary: #10b981 to #059669
Background: #064e3b
```

**Creative Orange**:
```css
Primary: #f97316 to #ea580c
Background: #9a3412
```

**Tech Purple**:
```css
Primary: #a855f7 to #9333ea
Background: #581c87
```

**Health Red**:
```css
Primary: #ef4444 to #dc2626
Background: #7f1d1d
```

### Status Badge Styles

Create custom badge colors for different states:
```css
.status-badge.custom {
    background: #your-background-color;
    color: #your-text-color;
}
```

**Example Badge Types**:
- `.status-badge.primary` - Primary app color
- `.status-badge.success` - Green for success/complete
- `.status-badge.warning` - Yellow/orange for warnings
- `.status-badge.error` - Red for errors
- `.status-badge.info` - Blue for information

### Logo Customization

**Option 1: Text Logo**
```html
<div class="lockscreen-logo">AB</div>
```

**Option 2: Emoji Logo**
```html
<div class="lockscreen-logo">🚀</div>
```

**Option 3: Image Logo**
```html
<div class="lockscreen-logo">
    <img src="logo.png" alt="App Logo" style="width: 100%; height: 100%; object-fit: contain;">
</div>
```

**Option 4: SVG Logo**
```html
<div class="lockscreen-logo">
    <svg><!-- Your SVG code --></svg>
</div>
```

## Use Cases by Industry

### E-Commerce App
- **Lock Screen**: "New order received"
- **Home Screen**: Order statuses (Processing, Shipped, Delivered)
- **Notification**: "Your order has shipped!"
- **Live Activity**: Package delivery tracking

### Fitness App
- **Lock Screen**: "Workout reminder"
- **Home Screen**: Today's stats (Steps, Calories, Active Minutes)
- **Notification**: "You reached your goal!"
- **Live Activity**: Workout in progress

### Food Delivery App
- **Lock Screen**: "Order update"
- **Home Screen**: Active orders with status
- **Notification**: "Your order is ready!"
- **Live Activity**: Delivery tracking

### Social Media App
- **Lock Screen**: "New message"
- **Home Screen**: Unread messages, likes, followers
- **Notification**: "Someone liked your post"
- **Live Activity**: Live video streaming

### Banking App
- **Lock Screen**: "Transaction alert"
- **Home Screen**: Account balances
- **Notification**: "Payment received"
- **Live Activity**: Transfer in progress

### Weather App
- **Lock Screen**: Current temperature
- **Home Screen**: Today's forecast
- **Notification**: "Severe weather alert"
- **Live Activity**: Storm tracking

## Widget Sizes

### Lock Screen Widgets
- **Circular**: 52x52 pt
- **Rectangular**: 160x72 pt
- **Inline**: Text only

### Home Screen Widgets
- **Small**: 155x155 pt
- **Medium**: 329x155 pt (included in template)
- **Large**: 329x345 pt
- **Extra Large**: 715x345 pt (iPad only)

## Implementation Checklist

- [ ] Replace all "APP" logos with your branding
- [ ] Update "Your App Name" with actual app name
- [ ] Customize color gradients to match brand
- [ ] Update widget titles and content
- [ ] Replace status items with real data
- [ ] Customize notification messages
- [ ] Update button actions and deep links
- [ ] Test all interactive elements
- [ ] Verify text is readable on all backgrounds
- [ ] Check color contrast for accessibility
- [ ] Test on different iPhone models
- [ ] Ensure all animations work smoothly

## Deep Linking Setup

Configure your app to handle deep links from widgets:

**URL Scheme Format**:
```
yourapp://[section]/[action]/[id]
```

**Examples**:
```
yourapp://home
yourapp://notifications/view/12345
yourapp://status/update
yourapp://tracking/live
```

**Implementation**:
```javascript
// Update button actions
function viewNotification() {
    window.location.href = 'yourapp://notifications/view';
}

function openSection(section) {
    window.location.href = `yourapp://${section}`;
}
```

## Data Integration

### Connecting to Your API

Replace static content with dynamic data:

```javascript
// Fetch widget data
async function updateWidget() {
    const response = await fetch('https://api.yourapp.com/widget-data');
    const data = await response.json();

    // Update lock screen
    document.querySelector('.lockscreen-content').textContent = data.title;
    document.querySelector('.lockscreen-detail').textContent = data.detail;

    // Update home screen status
    updateStatusRows(data.items);

    // Update live activity
    updateProgress(data.progress);
}
```

### Widget Refresh Strategy

```javascript
// Refresh widget data
const REFRESH_INTERVAL = 15 * 60 * 1000; // 15 minutes

setInterval(updateWidget, REFRESH_INTERVAL);
```

## Accessibility Features

### VoiceOver Labels

Add ARIA labels for screen readers:
```html
<div class="lockscreen-widget" aria-label="Lock screen widget showing app status">
    <div class="lockscreen-content" aria-label="Status: Your content here">
        Your Content
    </div>
</div>
```

### High Contrast Mode

Ensure text is readable:
```css
@media (prefers-contrast: high) {
    .lockscreen-widget {
        border: 2px solid #fff;
    }
    .lockscreen-content {
        font-weight: 700;
    }
}
```

### Reduced Motion

Respect user preferences:
```css
@media (prefers-reduced-motion: reduce) {
    * {
        animation: none !important;
        transition: none !important;
    }
}
```

## Testing Guide

### Browser Testing
1. Open HTML file in Safari (best iOS preview)
2. Test Chrome and Firefox for compatibility
3. Use responsive design mode (iPhone dimensions)

### Device Testing
1. Transfer to actual iPhone for testing
2. Test on different iPhone models (SE, 14, 15 Pro)
3. Test in dark mode
4. Test with different Dynamic Type sizes

### Interaction Testing
- [ ] All buttons respond to clicks/taps
- [ ] Notifications can be dismissed
- [ ] Progress bars animate smoothly
- [ ] Links open correctly
- [ ] Widgets display correctly on lock screen
- [ ] Home screen widgets are readable
- [ ] Live activities update in real-time

## Performance Optimization

### Image Optimization
```html
<!-- Use optimized images -->
<img src="logo.webp" alt="Logo" loading="lazy">
```

### CSS Optimization
- Minimize use of complex gradients
- Avoid heavy backdrop filters on older devices
- Use CSS transforms for animations (GPU accelerated)

### JavaScript Optimization
```javascript
// Use requestAnimationFrame for smooth animations
function updateProgress() {
    requestAnimationFrame(() => {
        // Update progress bar
    });
}
```

## Common Customization Tasks

### Change Widget Shape
```css
.lockscreen-widget {
    border-radius: 16px; /* Rounded */
    border-radius: 8px;  /* Less rounded */
    border-radius: 0;    /* Square */
}
```

### Add More Status Rows
```html
<!-- Copy and paste this block -->
<div class="status-row">
    <span class="status-label">New Item</span>
    <span class="status-badge primary">Status</span>
</div>
```

### Change Progress Speed
```javascript
// In the setInterval at bottom of HTML
setInterval(() => {
    // Change 2000 to your desired milliseconds
}, 2000); // 2 seconds
```

### Add Custom Fonts
```html
<link href="https://fonts.googleapis.com/css2?family=Your+Font&display=swap" rel="stylesheet">
```

```css
body {
    font-family: 'Your Font', -apple-system, sans-serif;
}
```

## Troubleshooting

### Widgets Not Displaying
- Check that HTML structure is intact
- Verify CSS classes are correct
- Ensure logo placeholders have content

### Colors Not Showing
- Check gradient syntax
- Verify hex color codes are valid
- Test in different browsers

### Buttons Not Working
- Check JavaScript function names match HTML onclick attributes
- Verify no console errors
- Test in browser developer tools

### Progress Bar Not Animating
- Ensure JavaScript is enabled
- Check browser console for errors
- Verify setInterval is running

## Resources

- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [WidgetKit Documentation](https://developer.apple.com/documentation/widgetkit)
- [iOS App Icon Template](https://developer.apple.com/design/resources/)
- [SF Symbols](https://developer.apple.com/sf-symbols/)

## Version History

- **v1.0** (November 2024): Initial blank template release
  - All 4 widget types included
  - Customizable placeholders
  - Interactive demo
  - Complete phone mockup
  - Documentation and examples

## Support

For questions or issues with this template:
1. Check the customization guide above
2. Verify all placeholders are replaced
3. Test in Safari for best iOS compatibility
4. Review the troubleshooting section

## License

This template is free to use for any project. Modify as needed for your specific requirements.

---

**Last Updated**: November 23, 2024
**Compatible with**: iOS 14+ (Widgets), iOS 16.1+ (Live Activities)
**Template Type**: Blank/Generic - Ready for customization
