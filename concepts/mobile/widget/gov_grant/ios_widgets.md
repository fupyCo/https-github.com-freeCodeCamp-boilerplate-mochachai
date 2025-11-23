# iOS Widgets - Government Grant Portal

## Overview

This file contains iOS widget mockups for the Government Grant Portal application. It showcases all four main iOS widget types with clean, minimalist design following Apple's Human Interface Guidelines.

## Widget Types Included

### 1. Lock Screen Widget
**Size**: Small (Circular or Rectangular)
**Use Case**: Quick glance information on the iPhone lock screen

**Features**:
- Application logo (GOV branding)
- Application status updates
- Quick counts and alerts
- Minimal design for lock screen visibility

**Example Use Cases**:
- "Application Update" - Shows status changes
- "My Apps" - Displays count of active applications
- "Deadline" - Shows days remaining until deadline

### 2. Home Screen Widget
**Size**: Medium (2x2 grid)
**Use Case**: Detailed information on the iPhone home screen

**Features**:
- Government Grant Portal branding with logo
- Application status list (up to 3 applications)
- Status badges (Pending, In Review, Approved)
- Last updated timestamp
- Clean card-based design

**Information Displayed**:
- Application numbers
- Current status of each application
- Color-coded status badges
- Auto-refresh indicator

### 3. Notification Banner
**Size**: Standard iOS notification
**Use Case**: Real-time alerts and updates

**Features**:
- App icon and name
- Timestamp ("now" or time ago)
- Notification title
- Detailed message
- Interactive buttons (Dismiss/View)
- Glassmorphism design with backdrop blur

**Interactive Elements**:
- **Dismiss Button**: Closes notification
- **View Button**: Opens app to relevant content
- Tap anywhere to open app

**Notification Types**:
- Application status changes
- New grant opportunities
- Deadline reminders
- Document requests

### 4. Live Activity (Dynamic Island)
**Size**: Expanded Dynamic Island
**Use Case**: Real-time progress tracking

**Features**:
- Government Grant Portal branding
- Live progress bar
- Step-by-step progress indicator
- Estimated time remaining
- Interactive action buttons
- Dark mode design

**Use Cases**:
- Application submission progress
- Document upload status
- Review process tracking
- Payment processing

## Design System

### Color Scheme
```css
Primary Blue: #26374a
Accent Red: #af3c43
Dark Background: #1c1c1e
Light Background: #ffffff
Text Primary: #000000
Text Secondary: #666666
Border/Divider: #e0e0e0
```

### Typography
- **Font Family**: -apple-system, SF Pro Display, SF Pro Text
- **Lock Screen**: 10-13px
- **Home Screen**: 13-16px
- **Notifications**: 12-14px
- **Live Activity**: 11-15px

### Spacing
- **Lock Screen**: Compact (8-12px padding)
- **Home Screen**: Comfortable (12-16px padding)
- **Notifications**: Standard (14px padding)
- **Live Activity**: Dynamic (12-20px padding)

### Status Badge Colors
```css
Pending: #fff3cd (background), #856404 (text)
In Review: #d1ecf1 (background), #0c5460 (text)
Approved: #d4edda (background), #155724 (text)
```

## Interactive Features

### Notification Buttons
1. **Dismiss**: Closes notification with slide-up animation
2. **View**: Opens app to application details page

### Live Activity Buttons
1. **Cancel**: Stops current process (with confirmation)
2. **View Details**: Opens app to detailed progress view

### Widget Taps
- Tapping any widget opens the Grant Portal app
- Deep links to relevant sections (applications, status, etc.)

## Phone Mockup

The template includes a complete iPhone mockup showing:
- **Lock screen** with time (9:41) and date
- **Notification banner** at the top
- **Lock screen widgets** at the bottom
- **Dynamic Island** area (for compatible devices)
- Realistic iPhone design with notch

## Customization Guide

### Changing Logo
Replace the logo placeholder:
```html
<div class="lockscreen-logo">GOV</div>
<!-- Replace with -->
<div class="lockscreen-logo">
    <img src="your-logo.png" alt="Logo">
</div>
```

### Updating Application Data
Modify the status rows in home screen widget:
```html
<div class="status-row">
    <span class="status-label">Application #XXXXX</span>
    <span class="status-badge [pending|review|approved]">Status</span>
</div>
```

### Customizing Notifications
Update notification content:
```html
<div class="notification-title">Your Title</div>
<div class="notification-message">Your message here...</div>
```

### Adjusting Progress
Change the Live Activity progress percentage:
```html
<div class="live-activity-progress-bar" style="width: 65%;"></div>
<!-- Change 65% to your desired percentage -->
```

## Implementation Notes

### Widget Refresh
- **Lock Screen**: Updates every 15-30 minutes
- **Home Screen**: Updates every 5-15 minutes
- **Live Activity**: Real-time updates
- **Notifications**: Instant delivery

### Deep Linking
Each widget should deep link to specific app sections:
```
grant://applications/45821
grant://apply
grant://status
grant://deadlines
```

### WidgetKit Integration
For actual iOS development:
1. Use SwiftUI for widget views
2. Implement TimelineProvider for updates
3. Configure widget families (small, medium, large)
4. Set up App Intents for interactive elements

### Data Requirements

**API Endpoints Needed**:
- `GET /api/applications/status` - Application statuses
- `GET /api/notifications/recent` - Latest notifications
- `GET /api/deadlines` - Upcoming deadlines
- `POST /api/applications/track` - Track submission progress

**Data Refresh**:
- Background fetch every 15 minutes
- Push notifications for instant updates
- Manual refresh on app open

## Accessibility

### VoiceOver Support
All widgets include proper labels:
- Logo: "Government Grant Portal logo"
- Status badges: "Status: Approved" (includes status in label)
- Buttons: "View application", "Dismiss notification"
- Progress: "Processing application, 65% complete, step 3 of 4"

### Dynamic Type
- Fonts scale with user's system settings
- Minimum font size: 11px
- Maximum font size: 20px (for larger accessibility sizes)

### Color Contrast
All text meets WCAG AA standards:
- Lock screen: White text on dark background (≥7:1)
- Home screen: Dark text on white background (≥4.5:1)
- Status badges: High contrast text/background combinations

## Testing Checklist

- [ ] All widgets display correctly on iPhone 14, 15 Pro
- [ ] Notifications appear with proper timing
- [ ] Interactive buttons respond correctly
- [ ] Deep links navigate to correct app sections
- [ ] Widgets update with fresh data
- [ ] Dark mode support (if applicable)
- [ ] VoiceOver reads all elements correctly
- [ ] Dynamic type scales properly
- [ ] Live Activity updates in real-time
- [ ] Progress animations smooth and accurate

## Known Limitations

1. **Lock Screen Widgets**: Limited to small size and simple layouts
2. **Live Activities**: Only available on iOS 16.1+
3. **Interactive Elements**: Limited in lock screen widgets
4. **Update Frequency**: System-imposed limits on refresh rates
5. **Battery Impact**: Frequent updates may affect battery life

## Best Practices

### Content
- Keep text concise and scannable
- Use clear status indicators
- Show most important information first
- Include timestamps for context

### Performance
- Minimize widget complexity
- Cache data locally
- Use background fetch efficiently
- Optimize images and assets

### User Experience
- Provide clear call-to-actions
- Make interactive elements obvious
- Use consistent branding
- Respect notification preferences

## Future Enhancements

Consider adding:
1. **Widget Configuration**: Let users choose which applications to track
2. **Multiple Sizes**: Support small, medium, and large widgets
3. **Complication Support**: For Apple Watch
4. **Siri Integration**: "Hey Siri, what's my application status?"
5. **Smart Stack**: Automatic widget rotation based on time/context
6. **Focus Mode**: Custom widgets for different Focus modes

## Resources

- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [WidgetKit Documentation](https://developer.apple.com/documentation/widgetkit)
- [Live Activities Documentation](https://developer.apple.com/documentation/activitykit)
- [App Intents](https://developer.apple.com/documentation/appintents)

## Version History

- **v1.0** (November 2024): Initial release
  - Lock screen widget
  - Home screen widget (medium)
  - Notification banner
  - Live Activity
  - iPhone mockup
  - Interactive demos

---

**Last Updated**: November 23, 2024
**Compatible with**: iOS 14+ (Widgets), iOS 16.1+ (Live Activities)
