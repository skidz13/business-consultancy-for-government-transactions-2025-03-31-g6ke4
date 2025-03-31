# ConsultPro Landing Page - Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the ConsultPro business consultancy landing page. Written for beginners, it covers essential modifications while preserving the page's responsive design and functionality.

## Table of Contents
1. [Updating Text and Styling](#updating-text-and-styling)
2. [Managing Links](#managing-links)
3. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains the company name and navigation menu. To modify:

1. **Company Name**
```html
<!-- Located in the header section -->
<div class="text-2xl font-bold">ConsultPro</div>
```
- Replace "ConsultPro" with your company name
- Adjust font size by changing `text-2xl` to `text-xl` (smaller) or `text-3xl` (larger)

2. **Navigation Menu Items**
```html
<div class="hidden md:flex items-center space-x-8">
    <a href="#features" class="text-gray-700 hover:text-gray-900">Features</a>
    <a href="#benefits" class="text-gray-700 hover:text-gray-900">Benefits</a>
    <a href="#faq" class="text-gray-700 hover:text-gray-900">FAQ</a>
</div>
```
- Modify menu text by changing the text between `<a>` tags
- Keep `href` attributes matching section IDs (e.g., "#features")
- Style adjustments:
  - Change text color: Replace `text-gray-700` with colors like `text-blue-700`
  - Adjust spacing: Modify `space-x-8` to `space-x-4` (smaller) or `space-x-12` (larger)

### Hero Section
```html
<div class="relative z-10 text-center text-white max-w-4xl mx-auto px-6">
    <h1 class="text-4xl md:text-6xl font-bold leading-tight mb-6">
        Business Consultancy for Government Transactions
    </h1>
    <p class="text-xl md:text-2xl mb-8 text-gray-200">
        Bright. Precise. Professional. Minimalist
    </p>
</div>
```
- Update heading and tagline text
- Adjust text size:
  - Desktop: Change `md:text-6xl` for heading size
  - Mobile: Modify `text-4xl` for smaller screens
- Change spacing with `mb-6` (margin-bottom) classes

## Managing Links

### Internal Navigation Links
Current internal links use section IDs:
```html
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
```
To update:
1. Locate the section ID in the HTML:
```html
<section id="features" class="py-24 bg-white">
```
2. Ensure the `href` attribute matches the section `id`
3. Test by clicking - should smooth scroll to the section

### Call-to-Action (CTA) Links
Current placeholder:
```html
<a href="https://stripe.com/checkout" class="inline-block bg-blue-600...">
```
To update:
1. Replace `https://stripe.com/checkout` with your actual checkout or contact page
2. Maintain the existing classes for consistent styling
3. Test the link thoroughly before deployment

## Adding Privacy and Terms Pages

### Footer Link Setup
Current placeholder links:
```html
<div>
    <h4 class="text-lg font-semibold mb-4">Legal</h4>
    <ul class="space-y-2 text-gray-400">
        <li><a href="#" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

To implement:
1. Create new HTML files:
   - `privacy.html`
   - `terms.html`
2. Update the href attributes:
```html
<li><a href="privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

### Common Issues and Solutions

1. **Broken Navigation**
- Check that section IDs match exactly with href attributes
- Verify no spaces in IDs
- Example fix:
```html
<!-- Incorrect -->
<section id="features section">
<a href="#features-section">

<!-- Correct -->
<section id="features">
<a href="#features">
```

2. **Responsive Design Issues**
- Always maintain both mobile and desktop classes:
```html
<!-- Keep both sizes -->
<h1 class="text-4xl md:text-6xl">

<!-- Don't remove mobile size -->
<h1 class="md:text-6xl"> <!-- Incorrect -->
```

3. **Style Inconsistencies**
- Copy existing button styles for new buttons:
```html
class="inline-block bg-blue-600 text-white px-8 py-4 rounded-full hover:bg-blue-700 transition-all duration-300"
```
- Maintain color scheme using Tailwind's color classes:
  - Primary: `blue-600`
  - Text: `gray-700`
  - Background: `white`, `gray-50`, `gray-900`

Remember to test all changes across different screen sizes using browser developer tools before deploying updates.