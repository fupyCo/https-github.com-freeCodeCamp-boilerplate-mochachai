# iOS Widgets - Contractor Directory App

## Overview

This file contains iOS widget mockups for the Contractor Directory App. It showcases all four main iOS widget types with clean, minimalist design following Apple's Human Interface Guidelines, specifically tailored for a local services and contractor directory application.

## Widget Types Included

### 1. Lock Screen Widget
**Size**: Small (Circular or Rectangular)
**Use Case**: Quick glance at active jobs and new requests

**Features**:
- Contractor app logo (hammer icon)
- Job request notifications
- Active job count
- Saved favorites count
- Real-time updates

**Example Use Cases**:
- "New Job Request" - Shows incoming service requests
- "Active Jobs" - Displays current pending jobs
- "Saved" - Quick access to favorite contractors

### 2. Home Screen Widget
**Size**: Medium (2x2 grid)
**Use Case**: Browse nearby contractors and services

**Features**:
- Contractor app branding with hammer logo
- List of nearby services (up to 3 contractors)
- Distance from user location
- Availability status
- Star ratings
- Auto-refresh with location updates

**Information Displayed**:
- Contractor name
- Service type (plumbing, electric, landscaping)
- Distance in miles
- Availability ("Available now" or opening hours)
- Rating (out of 5 stars)
- Last updated timestamp

### 3. Notification Banner
**Size**: Standard iOS notification
**Use Case**: Service updates and contractor messages

**Features**:
- App icon with hammer emoji
- Timestamp ("now", "2m ago", etc.)
- Notification title
- Detailed message
- Interactive buttons (Dismiss/Track or Dismiss/Reply)
- Glassmorphism design with backdrop blur

**Interactive Elements**:
- **Dismiss Button**: Closes notification
- **Track Button**: Opens live location tracking
- **Reply Button**: Opens messaging interface
- Tap anywhere to open app

**Notification Types**:
- Service request accepted/declined
- Contractor arrival updates
- Messages from contractors
- Job completion notifications
- Review reminders

### 4. Live Activity (Dynamic Island)
**Size**: Expanded Dynamic Island
**Use Case**: Real-time contractor tracking

**Features**:
- Contractor logo and service icon
- Live distance tracking
- Estimated arrival time
- Progress bar showing journey
- Interactive action buttons (Call/Track)
- Dark mode design
- Updates every 30 seconds

**Use Cases**:
- Contractor en route tracking
- Service in progress updates
- Real-time ETA calculations
- Job completion countdown

## Design System

### Color Scheme
```css
Primary Dark: #2c3e50
Accent Orange: #e76f51
Secondary Orange: #f4a261
Background: #ffffff
Text Primary: #000000
Text Secondary: #666666
Border/Divider: #e0e0e0
Icon Background: #e8f0f7
```

### Typography
- **Font Family**: -apple-system, SF Pro Display, SF Pro Text
- **Lock Screen**: 10-13px
- **Home Screen**: 11-16px
- **Notifications**: 12-14px
- **Live Activity**: 11-15px

### Spacing
- **Lock Screen**: Compact (8-12px padding)
- **Home Screen**: Comfortable (12-16px padding)
- **Notifications**: Standard (14px padding)
- **Live Activity**: Dynamic (12-20px padding)

### Service Icons
```
🔧 Plumbing
⚡ Electrical
🌳 Landscaping
🏠 Home Repair
🎨 Painting
🧹 Cleaning
```

## Interactive Features

### Notification Buttons
1. **Dismiss**: Closes notification
2. **Track**: Opens live map with contractor location
3. **Reply**: Opens messaging to communicate with contractor
4. **Call**: Initiates phone call to contractor

### Live Activity Buttons
1. **Call**: Direct phone call to contractor
2. **Track**: Opens detailed map view with ETA

### Widget Taps
- Tapping any widget opens the Contractor Directory app
- Deep links to relevant sections:
  - Active jobs
  - Nearby services
  - Messages
  - Tracking map

## Phone Mockup

The template includes a complete iPhone mockup showing:
- **Lock screen** with time (9:41) and date
- **Notification banner** for contractor messages
- **Lock screen widgets** showing active jobs and favorites
- **Dynamic Island** area with live tracking
- Realistic iPhone design with notch

## Customization Guide

### Changing Service Icons
Update the emoji icons:
```html
<div class="service-icon">🔧</div>
<!-- Replace with your preferred emoji or image -->
```

### Updating Contractor Data
Modify the service rows in home screen widget:
```html
<div class="service-row">
    <div class="service-icon">🔧</div>
    <div class="service-info">
        <div class="service-name">Contractor Name</div>
        <div class="service-detail">X.X mi away • Status</div>
    </div>
    <div class="service-rating">★ X.X</div>
</div>
```

### Customizing Notifications
Update notification content:
```html
<div class="notification-title">Your Title</div>
<div class="notification-message">Your message here...</div>
```

### Adjusting Distance/ETA
Change the Live Activity tracking info:
```html
<div class="live-activity-detail">X.X mi away • Arriving in XX minutes</div>
```

## Implementation Notes

### Widget Refresh
- **Lock Screen**: Updates when job status changes
- **Home Screen**: Updates based on user location (every 5-15 minutes)
- **Live Activity**: Real-time updates every 30 seconds during active tracking
- **Notifications**: Instant delivery via push notifications

### Location Services
Widgets require location permission to show:
- Distance to contractors
- Nearby services
- Real-time tracking
- Arrival estimates

### Deep Linking
Each widget should deep link to specific app sections:
```
contractor://jobs/active
contractor://nearby
contractor://messages
contractor://track/[contractor-id]
contractor://profile/[contractor-id]
```

### API Endpoints Needed

**For Widgets**:
- `GET /api/contractors/nearby?lat=X&lon=Y` - Get nearby contractors
- `GET /api/jobs/active` - Get active job requests
- `GET /api/jobs/{id}/status` - Get job status
- `GET /api/favorites` - Get saved contractors

**For Live Activity**:
- `GET /api/tracking/{contractor_id}/location` - Real-time location
- `GET /api/tracking/{contractor_id}/eta` - Estimated arrival time
- `POST /api/tracking/{contractor_id}/cancel` - Cancel tracking

**For Notifications**:
- Push notification service for real-time updates
- WebSocket for live tracking updates

## Use Case Scenarios

### Scenario 1: Finding a Plumber
1. User opens home screen widget
2. Sees "Smith Plumbing" 0.3 mi away, available now
3. Taps widget to open app
4. Books service request

### Scenario 2: Tracking Arrival
1. Contractor accepts job
2. Notification appears: "Smith Plumbing has accepted your request"
3. User taps "Track" button
4. Live Activity starts showing real-time location
5. Progress bar updates as contractor approaches
6. Arrival notification when contractor is close

### Scenario 3: Emergency Service
1. Lock screen widget shows "New Job Request"
2. User can quickly see available contractors
3. Tap widget to immediately request service
4. Get instant notifications when contractor responds

## Accessibility

### VoiceOver Support
All widgets include proper labels:
- Logo: "Contractor Directory app logo"
- Service entries: "Smith Plumbing, 0.3 miles away, 4.8 star rating, Available now"
- Buttons: "Track contractor location", "Call contractor", "Dismiss notification"
- Progress: "Contractor en route, 40% complete, 2.4 miles away, arriving in 12 minutes"

### Dynamic Type
- Fonts scale with user's system settings
- Minimum font size: 11px
- Maximum font size: 20px

### Color Contrast
All text meets WCAG AA standards:
- Lock screen: White text on dark background (≥7:1)
- Home screen: Dark text on white background (≥4.5:1)
- Ratings: Sufficient contrast for visibility

## Testing Checklist

- [ ] Location permission handling
- [ ] Widgets update with current location
- [ ] Distance calculations are accurate
- [ ] ETA updates in real-time during tracking
- [ ] Notifications appear with correct timing
- [ ] Interactive buttons work correctly
- [ ] Deep links navigate to correct screens
- [ ] Ratings display correctly
- [ ] Availability status is accurate
- [ ] Dark mode support
- [ ] VoiceOver reads all elements
- [ ] Dynamic type scales properly

## Privacy Considerations

### Location Privacy
- Explain why location is needed in widget configuration
- Allow users to disable location-based features
- Don't store location history
- Clear location data when widget is removed

### Contractor Information
- Only show publicly available contractor data
- Respect contractor privacy settings
- Don't share user location with contractors until job is accepted

## Best Practices

### Content
- Show most relevant contractors first (by distance and rating)
- Keep messages concise
- Include accurate ETAs
- Update arrival times frequently
- Clear status indicators

### Performance
- Cache contractor data locally
- Use efficient location updates
- Minimize battery impact of live tracking
- Optimize image assets

### User Experience
- Provide clear call-to-actions
- Make tracking information easy to understand
- Use familiar icons and symbols
- Respect notification preferences
- Allow easy dismissal of updates

## Future Enhancements

Consider adding:
1. **Widget Customization**: Let users choose which service types to show
2. **Multiple Sizes**: Support small and large widgets
3. **Apple Watch**: Contractor tracking on watch
4. **Siri Integration**: "Hey Siri, find a plumber near me"
5. **Smart Suggestions**: Proactive widget showing contractors before user needs them
6. **Job History**: Widget showing recent contractors for quick re-booking
7. **Price Estimates**: Show estimated cost ranges in widget
8. **Availability Calendar**: See contractor schedules at a glance

## Integration with Contractor App Features

### Job Booking Flow
1. Widget shows nearby contractors
2. User taps to view details
3. Books service through app
4. Receives confirmation notification
5. Live Activity starts when contractor is en route

### Messaging Integration
- Receive contractor messages as notifications
- Reply directly from notification
- Message history accessible from widget tap

### Rating System
- Prompt for rating after job completion
- Ratings update in home screen widget
- High-rated contractors prioritized

## Resources

- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [WidgetKit Documentation](https://developer.apple.com/documentation/widgetkit)
- [Live Activities Documentation](https://developer.apple.com/documentation/activitykit)
- [CoreLocation Framework](https://developer.apple.com/documentation/corelocation)

## Version History

- **v1.0** (November 2024): Initial release
  - Lock screen widget with job updates
  - Home screen widget with nearby contractors
  - Notification banner for messages and updates
  - Live Activity for contractor tracking
  - iPhone mockup with realistic preview
  - Interactive demos with animations

---

**Last Updated**: November 23, 2024
**Compatible with**: iOS 14+ (Widgets), iOS 16.1+ (Live Activities)
**Location Services**: Required for distance and tracking features
