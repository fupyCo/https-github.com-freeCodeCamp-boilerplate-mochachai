# Newspaper Dynamic Text Box Template

## Overview

A vintage newspaper classifieds-style dynamic text box template that automatically updates content based on search parameters. Designed to replicate the authentic look and feel of traditional newspaper classified ads with aged paper texture, bold borders, and classic typography.

## Visual Design Features

### 🗞️ Authentic Newspaper Styling

- **Aged Paper Background**: Cream/beige gradient background with subtle texture overlay
- **Classic Typography**: Times New Roman serif fonts throughout
- **Bold Borders**: 3-4px solid black borders around all ad boxes
- **Newspaper Masthead**: Traditional newspaper header with "THE CLASSIFIEDS" title
- **Dense Text Layout**: Compact, justified text like real classified ads
- **Box Shadows**: 3D effect on ad boxes for depth
- **Ornamental Elements**: Classic newspaper decorative elements (❦)

### 🎨 Color Scheme

- **Background**: `#faf7f0` (aged paper white)
- **Accent Background**: `#e8dcc8` (vintage beige)
- **Text**: `#1a1a1a` (near black)
- **Borders**: `#000000` (solid black)
- **Dynamic Values**: `#fff9e6` (highlighted cream)
- **Featured Sections**: Black background with white text

## Dynamic Text Boxes Included

### 1. Featured Large Ad (Full-Width)
**Category**: ★ Featured Service ★
**Use Case**: Premium placement, main service offering
**Layout**: Full-width featured box with highlight sections

```html
<div class="ad-box featured">
    <div class="ad-title">
        Professional <span class="dynamic-value" data-field="service-title">Plumber</span> Services
    </div>
    <div class="ad-subtitle">
        Serving <span class="dynamic-value" data-field="location">Upstate New York</span>
    </div>
</div>
```

**Dynamic Fields Used**:
- `service-title` - Capitalized service name
- `location` - Service location
- `rating` - Star rating
- `urgency-text` - Service urgency level
- `service-plural` - Plural form of service

### 2. Help Wanted Style Ad
**Category**: Help Wanted
**Use Case**: Job listings, contractor recruitment
**Layout**: Half-width box with bulleted list

**Dynamic Fields Used**:
- `service-plural-title` - Capitalized plural service
- `location` - Job location
- `rating` - Required rating
- `urgency-text-title` - Capitalized urgency

### 3. Service Directory Ad
**Category**: Service Directory
**Use Case**: General service listings, directories
**Layout**: Half-width box with descriptive text

**Dynamic Fields Used**:
- `service-title` - Service name
- `service-plural` - Multiple professionals
- `location` - Service area
- `rating` - Minimum rating
- `urgency-text-title` - Service timing

### 4. Testimonial/Review Style Ad
**Category**: Customer Reviews
**Use Case**: Social proof, testimonials
**Layout**: Half-width box with quoted reviews

**Dynamic Fields Used**:
- `service-plural-title` - Professional type
- `service` - Service name
- `location` - Review location
- `rating` - Star rating
- `urgency-text` - Service speed

### 5. Quick Info Ad
**Category**: Local Services
**Use Case**: Short, punchy service ads
**Layout**: Half-width box with highlight box

**Dynamic Fields Used**:
- `service-title` - Service type
- `service-plural` - Multiple professionals
- `location` - Service area
- `rating` - Star rating
- `urgency-text-title` - Timing

### 6. Special Offer Ad
**Category**: ★ Special Offer ★
**Use Case**: Promotions, discounts
**Layout**: Half-width box with offer highlight

**Dynamic Fields Used**:
- `service-title` - Service name
- `service-plural` - Professional type
- `location` - Offer location
- `rating` - Rating requirement
- `urgency-text-title` - Service timing

### 7. Complete Service Guide (Full-Width Bottom)
**Category**: Complete Service Guide
**Use Case**: SEO-optimized comprehensive description
**Layout**: Full-width detailed ad with multiple paragraphs

**Dynamic Fields Used**: All fields (comprehensive)

## Dynamic Field Reference

### Available Data Fields

| Field Name | Description | Example Output |
|------------|-------------|----------------|
| `service` | Service name (lowercase) | plumber |
| `service-plural` | Plural form (lowercase) | plumbers |
| `service-title` | Capitalized service | Plumber |
| `service-plural-title` | Capitalized plural | Plumbers |
| `location` | Location as entered | Upstate New York |
| `urgency-text` | Urgency (lowercase) | next day |
| `urgency-text-title` | Urgency (capitalized) | Next Day |
| `rating` | Rating with + sign | 4+ |

### HTML Usage

```html
<span class="dynamic-value" data-field="service">plumber</span>
<span class="dynamic-value" data-field="location">Upstate New York</span>
<span class="dynamic-value" data-field="rating">4+</span>
```

## Search Parameters

### Form Fields

1. **Service Type** (text input)
   - Examples: plumber, electrician, contractor, landscaper
   - Automatically generates plural and capitalized variations

2. **Location** (text input)
   - Examples: Upstate New York, Brooklyn, Manhattan
   - Used as-is throughout ads

3. **Urgency Level** (dropdown)
   - `emergency` → "emergency"
   - `same-day` → "same day"
   - `next-day` → "next day"
   - `scheduled` → "scheduled"

4. **Minimum Rating** (dropdown)
   - `any` → "all"
   - `3` → "3+"
   - `4` → "4+"
   - `5` → "5 Stars Only"

## CSS Classes Reference

### Ad Box Structure

```css
.ad-box                 /* Individual classified ad container */
.ad-box.featured        /* Full-width featured ad */
.ad-header              /* Ad header section */
.ad-category            /* Category label */
.ad-title               /* Main ad title */
.ad-subtitle            /* Secondary title/location */
.ad-body                /* Main ad content */
```

### Special Elements

```css
.dynamic-value          /* Highlighted dynamic text */
.highlight-box          /* Black box with white text */
.contact-box            /* Dashed border contact info */
.copy-btn               /* Copy to clipboard button */
```

### Layout Classes

```css
.newspaper-container    /* Main wrapper */
.masthead               /* Newspaper header */
.section-header         /* "CLASSIFIEDS" section */
.classifieds-grid       /* 2-column ad grid */
.control-panel          /* Search form area */
```

## Customization Guide

### 1. Adding New Ad Boxes

```html
<div class="ad-box" id="ad8">
    <button class="copy-btn" onclick="copyAd('ad8')">Copy</button>
    <div class="ad-header">
        <div class="ad-category">Your Category</div>
        <div class="ad-title">Your Title Here</div>
    </div>
    <div class="ad-body">
        <p>Your content with <span class="dynamic-value" data-field="service">dynamic</span> values.</p>
    </div>
</div>
```

### 2. Customizing Colors

```css
/* Change aged paper color */
.newspaper-container {
    background: #your-color;
}

/* Change border color */
.ad-box {
    border-color: #your-border-color;
}

/* Change dynamic value highlight */
.dynamic-value {
    background: #your-highlight-color;
    border-bottom-color: #your-underline-color;
}
```

### 3. Adjusting Typography

```css
/* Change font family */
body {
    font-family: 'Georgia', 'Times New Roman', serif;
}

/* Adjust ad title size */
.ad-title {
    font-size: 20px; /* default: 18px */
}

/* Change body text size */
.ad-body {
    font-size: 13px; /* default: 12px */
}
```

### 4. Modifying Layout

```css
/* Change to 3-column layout */
.classifieds-grid {
    grid-template-columns: repeat(3, 1fr);
}

/* Single column layout */
.classifieds-grid {
    grid-template-columns: 1fr;
}

/* Adjust spacing between ads */
.classifieds-grid {
    gap: 30px; /* default: 20px */
}
```

### 5. Custom Pluralization

Add custom plural forms in JavaScript:

```javascript
function pluralize(word) {
    const exceptions = {
        'plumber': 'plumbers',
        'electrician': 'electricians',
        'your-word': 'your-custom-plural',
        'handyman': 'handymen', // irregular
        'hvac': 'HVAC technicians' // acronym
    };
    return exceptions[word] || word + 's';
}
```

## How to Use

### Method 1: Interactive Demo

1. Open `newspaper_dynamic_textbox.html` in a web browser
2. Use the "Customize Your Search" control panel
3. Enter your service, location, urgency, and rating
4. Click "Update Classifieds" to see all ads update
5. Click "Copy" button on any ad to copy its HTML

### Method 2: Integrate Into Your Project

**Step 1**: Copy the CSS styles into your stylesheet

**Step 2**: Add HTML ad boxes to your page

**Step 3**: Include the JavaScript functions

**Step 4**: Call the update function with your parameters

```javascript
const params = {
    service: 'electrician',
    location: 'Brooklyn',
    urgency: 'emergency',
    rating: '5'
};

updateClassifieds(params);
```

### Method 3: URL Parameters

Share links with embedded search:

```
newspaper_dynamic_textbox.html?service=electrician&location=Brooklyn&urgency=emergency&rating=5
```

The template automatically loads and applies URL parameters.

## JavaScript Functions

### Core Functions

#### `updateClassifieds(params)`
Main function to update all dynamic text boxes.

```javascript
updateClassifieds({
    service: 'plumber',
    location: 'Manhattan',
    urgency: 'next-day',
    rating: '4'
});
```

#### `pluralize(word)`
Converts singular service names to plural.

```javascript
pluralize('plumber')      // Returns: 'plumbers'
pluralize('electrician')  // Returns: 'electricians'
pluralize('handyman')     // Returns: 'handymen'
```

#### `capitalize(str)`
Capitalizes first letter of a string.

```javascript
capitalize('plumber')     // Returns: 'Plumber'
capitalize('next day')    // Returns: 'Next day'
```

#### `copyAd(adId)`
Copies ad HTML to clipboard.

```javascript
copyAd('ad1')  // Copies content of ad box #1
```

#### `loadFromURL()`
Loads search parameters from URL query string.

```javascript
loadFromURL()  // Reads ?service=plumber&location=Brooklyn...
```

#### `updateURL(params)`
Updates browser URL with current search parameters.

```javascript
updateURL(currentParams)  // Updates URL bar
```

## Use Cases

### 1. Service Directory Website

Perfect for local service directories where users search for professionals.

```javascript
const params = {
    service: 'landscaper',
    location: 'Long Island',
    urgency: 'scheduled',
    rating: '4'
};
```

**Result**: All 7 ad boxes display landscaping services in Long Island with 4+ stars.

### 2. Job Board

Display job listings in classic newspaper style.

```javascript
const params = {
    service: 'carpenter',
    location: 'Queens',
    urgency: 'immediate',
    rating: 'any'
};
```

**Result**: Help Wanted style ads for carpenters in Queens.

### 3. Real Estate Classifieds

List properties with newspaper aesthetic.

```javascript
const params = {
    service: 'apartment',
    location: 'Brooklyn Heights',
    urgency: 'available now',
    rating: '5'
};
```

### 4. Local Business Directory

Classic classified ads for various businesses.

```javascript
const params = {
    service: 'restaurant',
    location: 'Manhattan',
    urgency: 'open today',
    rating: '4'
};
```

### 5. Event Listings

Newspaper-style event announcements.

```javascript
const params = {
    service: 'concert',
    location: 'Madison Square Garden',
    urgency: 'this weekend',
    rating: 'any'
};
```

## Advanced Features

### 1. Auto-Update Date

The masthead automatically displays the current date:

```javascript
function updateDate() {
    const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
    const today = new Date();
    document.getElementById('currentDate').textContent = today.toLocaleDateString('en-US', options);
}
```

**Output**: "Sunday, November 24, 2024"

### 2. URL Parameter Sharing

Users can share specific searches via URL:

```
https://yoursite.com/classifieds?service=electrician&location=Brooklyn&urgency=emergency&rating=5
```

This enables:
- Bookmarkable searches
- Social media sharing
- Email links
- SEO-friendly URLs

### 3. Copy to Clipboard

Each ad has a "Copy" button that copies the ad's HTML:

```javascript
function copyAd(adId) {
    const ad = document.getElementById(adId);
    const adContent = ad.querySelector('.ad-body').innerHTML;
    navigator.clipboard.writeText(adContent);
}
```

### 4. Print Stylesheet

Optimized for printing - hides control panel and copy buttons:

```css
@media print {
    .control-panel,
    .copy-btn,
    .code-section {
        display: none;
    }
}
```

### 5. Responsive Design

Automatically adjusts to mobile screens:

```css
@media (max-width: 768px) {
    .classifieds-grid {
        grid-template-columns: 1fr;  /* Single column */
    }
    .masthead h1 {
        font-size: 36px;  /* Smaller header */
    }
}
```

## SEO Optimization

### Dynamic Meta Tags

Update page meta tags based on search:

```javascript
document.title = `${serviceTitle} in ${location} - Classifieds`;

const metaDesc = document.querySelector('meta[name="description"]');
metaDesc.content = `Find ${servicePlural} in ${location}. ${rating} star rated professionals.`;
```

### Structured Data

Add JSON-LD structured data for search engines:

```html
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "Service",
    "name": "Plumber Services",
    "areaServed": "Upstate New York",
    "aggregateRating": {
        "@type": "AggregateRating",
        "ratingValue": "4"
    }
}
</script>
```

### Best Practices

- ✅ Unique content for each search combination
- ✅ Proper heading hierarchy (H1 → H2 → H3)
- ✅ Descriptive alt text for images (if added)
- ✅ Semantic HTML structure
- ✅ Fast page load time (no external dependencies)
- ✅ Mobile-friendly responsive design

## Performance Optimization

### No External Dependencies

- Pure JavaScript (no jQuery, React, etc.)
- Embedded CSS (no external stylesheets)
- No image files required
- **Total file size**: ~40KB

### Fast Updates

Dynamic updates are instant:

```javascript
// Updates all dynamic values in milliseconds
Object.keys(fields).forEach(field => {
    document.querySelectorAll(`[data-field="${field}"]`).forEach(el => {
        el.textContent = fields[field];
    });
});
```

### Efficient Selectors

Uses data attributes for clean, fast selection:

```html
<span data-field="service">plumber</span>
```

```javascript
document.querySelectorAll(`[data-field="service"]`)
```

## Browser Compatibility

### Supported Browsers

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile Safari (iOS 14+)
- ✅ Chrome Mobile (Android 90+)

### Required Features

- `querySelector` / `querySelectorAll`
- `URLSearchParams`
- `navigator.clipboard` (for copy function)
- CSS Grid Layout
- CSS Flexbox

### Fallbacks

For older browsers without clipboard API:

```javascript
if (!navigator.clipboard) {
    // Use document.execCommand('copy') fallback
    const textarea = document.createElement('textarea');
    textarea.value = content;
    document.body.appendChild(textarea);
    textarea.select();
    document.execCommand('copy');
    document.body.removeChild(textarea);
}
```

## Troubleshooting

### Issue: Dynamic values not updating

**Cause**: `data-field` attribute doesn't match JavaScript field name

**Solution**: Ensure exact match:
```javascript
'service-plural'  // JavaScript
```
```html
data-field="service-plural"  <!-- HTML -->
```

### Issue: Plural forms incorrect

**Cause**: Word not in exceptions dictionary

**Solution**: Add to `pluralize()` function:
```javascript
const exceptions = {
    'your-word': 'correct-plural'
};
```

### Issue: Layout breaks on mobile

**Cause**: Viewport meta tag missing

**Solution**: Add to `<head>`:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Issue: Copy button doesn't work

**Cause**: Page not served over HTTPS

**Solution**: Use HTTPS or localhost (required for clipboard API)

### Issue: URL parameters not loading

**Cause**: `loadFromURL()` called after `updateClassifieds()`

**Solution**: Call in correct order:
```javascript
loadFromURL();              // First
updateClassifieds(params);  // Second
```

### Issue: Fonts look different

**Cause**: Times New Roman not available on system

**Solution**: Add font stack with fallbacks:
```css
font-family: 'Times New Roman', Georgia, 'DejaVu Serif', serif;
```

## Accessibility

### ARIA Labels

Add descriptive labels for screen readers:

```html
<div class="ad-box" role="article" aria-label="Classified advertisement">
    <span class="dynamic-value" data-field="service"
          aria-label="Service type">plumber</span>
</div>
```

### Keyboard Navigation

All interactive elements are keyboard accessible:

- Form inputs: Tab navigation
- Submit button: Enter key
- Copy buttons: Tab + Enter/Space

### Focus Management

Visible focus indicators on all interactive elements:

```css
button:focus,
input:focus,
select:focus {
    outline: 3px solid #000;
    outline-offset: 2px;
}
```

### Screen Reader Announcements

Announce updates to assistive technology:

```javascript
// Create live region
const liveRegion = document.createElement('div');
liveRegion.setAttribute('role', 'status');
liveRegion.setAttribute('aria-live', 'polite');
liveRegion.textContent = 'Classifieds updated';
document.body.appendChild(liveRegion);
```

## Comparison with Modern Template

| Feature | Newspaper Template | Modern Template (dynamic_text_blocks.html) |
|---------|-------------------|-------------------------------------------|
| **Design Style** | Vintage newspaper | Modern gradient |
| **Typography** | Times New Roman serif | Sans-serif system fonts |
| **Color Scheme** | Black & white + aged paper | Purple/blue gradients |
| **Layout** | Bordered boxes, grid | Rounded cards, flowing |
| **Background** | Cream with texture | Purple gradient |
| **Borders** | Bold 3-4px solid black | Subtle shadows |
| **Text Style** | Dense, compact, justified | Spacious, left-aligned |
| **Headers** | Uppercase, condensed | Mixed case, modern |
| **Use Case** | Vintage/retro sites, classifieds | Modern web apps, SaaS |
| **File Size** | ~40KB | ~45KB |
| **Functionality** | Identical | Identical |

## Example Variations

### Variation 1: Real Estate Classifieds

```javascript
updateClassifieds({
    service: 'apartment',
    location: 'Upper West Side',
    urgency: 'immediate',
    rating: 'any'
});
```

**Result**:
- "Find the Best APARTMENT in Upper West Side"
- "Immediate move-in available"
- All ad boxes styled as apartment listings

### Variation 2: Job Board

```javascript
updateClassifieds({
    service: 'accountant',
    location: 'Financial District',
    urgency: 'hiring now',
    rating: '4'
});
```

**Result**: Help Wanted style ads for accountants

### Variation 3: Auto Classifieds

```javascript
updateClassifieds({
    service: 'mechanic',
    location: 'Brooklyn',
    urgency: 'same-day',
    rating: '5'
});
```

**Result**: Auto service classifieds

### Variation 4: Event Listings

```javascript
updateClassifieds({
    service: 'band',
    location: 'Greenwich Village',
    urgency: 'this weekend',
    rating: 'any'
});
```

**Result**: Entertainment classifieds

## Code Examples

### Example 1: Basic Integration

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Classifieds</title>
    <!-- Include newspaper CSS styles here -->
</head>
<body>
    <div class="ad-box">
        <div class="ad-title">
            <span class="dynamic-value" data-field="service-title">Plumber</span>
        </div>
        <div class="ad-body">
            <p>Find <span class="dynamic-value" data-field="service-plural">plumbers</span>
            in <span class="dynamic-value" data-field="location">your area</span>.</p>
        </div>
    </div>

    <script>
        updateClassifieds({
            service: 'plumber',
            location: 'Brooklyn',
            urgency: 'next-day',
            rating: '4'
        });
    </script>
</body>
</html>
```

### Example 2: Form Integration

```javascript
document.getElementById('myForm').addEventListener('submit', (e) => {
    e.preventDefault();

    const formData = new FormData(e.target);
    const params = {
        service: formData.get('service'),
        location: formData.get('location'),
        urgency: formData.get('urgency'),
        rating: formData.get('rating')
    };

    updateClassifieds(params);
});
```

### Example 3: API Integration

```javascript
async function searchServices(query) {
    const response = await fetch('/api/search', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(query)
    });

    const data = await response.json();

    // Update classifieds with search params
    updateClassifieds({
        service: data.service,
        location: data.location,
        urgency: data.urgency,
        rating: data.rating
    });

    // Display results
    displayResults(data.results);
}
```

## Testing Checklist

- [ ] Test with various service types (plumber, electrician, contractor)
- [ ] Test with different locations (city, state, region)
- [ ] Test all urgency levels (emergency, same-day, next-day, scheduled)
- [ ] Test all rating filters (any, 3+, 4+, 5)
- [ ] Verify URL parameters load correctly
- [ ] Test copy buttons on all 7 ad boxes
- [ ] Check mobile responsive design (phone, tablet)
- [ ] Verify print stylesheet hides control panel
- [ ] Test pluralization for edge cases
- [ ] Check special characters in inputs
- [ ] Test on different browsers (Chrome, Firefox, Safari, Edge)
- [ ] Verify keyboard navigation works
- [ ] Test with screen reader (accessibility)

## Version History

**v1.0** (November 24, 2024)
- Initial release
- 7 unique classified ad templates
- Vintage newspaper styling with aged paper effect
- Bold borders and classic typography
- URL parameter support
- Copy-to-clipboard functionality
- Fully responsive design
- Print-optimized stylesheet
- Complete documentation

## Related Files

- `newspaper_dynamic_textbox.html` - Main template file
- `dynamic_text_blocks.html` - Modern version template
- `dynamic_text_blocks.md` - Modern version documentation

## License

Free to use for any project, commercial or personal. Modify as needed for your specific requirements.

## Credits

**Design Inspiration**: Classic American newspaper classifieds (1950s-1990s)
**Typography**: Times New Roman (serif standard)
**Layout**: Traditional multi-column classified ad grid
**Color Palette**: Aged newsprint aesthetic

---

**Last Updated**: November 24, 2024
**Template Type**: Newspaper Classified Ads - Dynamic Text Box System
**Dependencies**: None (Pure JavaScript, CSS, HTML)
**File Size**: ~40KB
**Browser Support**: All modern browsers (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)
