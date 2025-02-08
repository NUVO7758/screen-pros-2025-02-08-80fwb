# SCREEN PROS Landing Page - Maintenance Guide

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the main navigation and logo. To update:

1. **Company Name/Logo**
```html
<!-- Find this line in the header -->
<a href="#" class="text-2xl font-bold tracking-wider text-white hover:text-purple-400 transition-colors">
    SCREEN PROS
</a>
```
- Replace "SCREEN PROS" with your company name
- Adjust text size by changing `text-2xl` to `text-xl` (smaller) or `text-3xl` (larger)

### Hero Section
The main landing section contains the primary heading and subtitle:

```html
<h1 class="text-4xl md:text-6xl lg:text-7xl font-bold mb-8 tracking-tight bg-clip-text text-transparent bg-gradient-to-r from-purple-400 to-pink-400">
    SCREEN PROS
</h1>
<p class="text-xl md:text-2xl lg:text-3xl text-gray-300 mb-12 tracking-wide">
    FAST, QUALITY, EFFICIENT SERVICE
</p>
```
- Update text between the tags
- The classes `md:text-6xl` and `lg:text-7xl` control text size on different screen sizes
- Don't remove `bg-clip-text` and `text-transparent` as they create the gradient effect

### Features Section
Each feature card follows this structure:
```html
<div class="bg-gray-900 p-8 rounded-2xl hover:transform hover:scale-105 transition-all duration-300 shadow-xl hover:shadow-purple-500/10">
    <h3 class="text-xl font-semibold mb-4 text-purple-400">Organic Materials</h3>
    <p class="text-gray-400">Environmentally conscious materials...</p>
</div>
```
To modify:
1. Change heading text between `<h3>` tags
2. Update description between `<p>` tags
3. Keep the classes intact to maintain hover effects

## Fixing Broken Links

### Navigation Menu Links
Current navigation links are:
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-300 hover:text-white transition-colors">Features</a>
    <a href="#benefits" class="text-gray-300 hover:text-white transition-colors">Benefits</a>
    <a href="#faq" class="text-gray-300 hover:text-white transition-colors">FAQ</a>
    <a href="#contact" class="text-gray-300 hover:text-white transition-colors">Contact</a>
</div>
```

To update:
1. The `href="#features"` format links to sections within the page
2. For external links, replace with full URL: `href="https://example.com"`
3. For internal pages, use relative paths: `href="./about.html"`

### CTA Button Link
```html
<a href={cta_link} class="inline-block bg-purple-600 hover:bg-purple-700 text-white font-semibold px-8 py-4 rounded-lg">
    Get Started
</a>
```
Replace `{cta_link}` with your actual link:
- External: `href="https://booking.example.com"`
- Internal: `href="./contact.html"`

## Linking Privacy and Terms Pages

### Footer Legal Links
Current placeholder links:
```html
<div>
    <h3 class="text-lg font-semibold mb-4">Legal</h3>
    <ul class="space-y-2 text-gray-400">
        <li><a href="#" class="hover:text-white transition-colors">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-white transition-colors">Terms of Service</a></li>
    </ul>
</div>
```

To add proper links:
1. Create privacy.html and terms.html in your root directory
2. Update the href attributes:
```html
<li><a href="./privacy.html" class="hover:text-white transition-colors">Privacy Policy</a></li>
<li><a href="./terms.html" class="hover:text-white transition-colors">Terms of Service</a></li>
```

## Troubleshooting

### Common Issues:

1. **Broken Internal Links**
- Ensure section IDs match href attributes
- Check for typos in IDs
- Verify file paths start with `./` for relative links

2. **Responsive Design Problems**
- Don't remove `md:` or `lg:` prefixes from classes
- Keep the `container` class on parent elements
- Maintain the `mx-auto` class for centering

3. **Style Issues**
- If gradient text disappears, verify these classes are present:
  ```html
  bg-clip-text text-transparent bg-gradient-to-r
  ```
- For hover effects, ensure all transition classes remain:
  ```html
  hover:transform hover:scale-105 transition-all duration-300
  ```

### Need Help?
- Check the [Tailwind CSS documentation](https://tailwindcss.com/docs)
- Verify all files are in the correct directory
- Test links in multiple browsers
- Ensure proper indentation for readability

Remember to always backup your code before making changes!