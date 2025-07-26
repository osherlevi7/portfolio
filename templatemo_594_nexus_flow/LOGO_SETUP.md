# Logo Setup Instructions

Your LionFish Consultant logo has been integrated into the website! Here's how to complete the setup:

## 🖼️ **Step 1: Add Your Logo File**

1. **Save your logo** to the `images` folder
2. **Name it** `lionfish-logo.png` (or update the HTML if you use a different name)
3. **Recommended format**: PNG with transparent background
4. **Recommended size**: At least 200x200px (will be scaled down automatically)

## 📁 **File Structure**
```
templatemo_594_nexus_flow/
├── images/
│   └── lionfish-logo.png    ← Add your logo here
├── index.html
├── templatemo-nexus-style.css
├── templatemo-nexus-scripts.js
└── README.md
```

## 🎨 **Logo Features**

Your logo will appear:
- **In the navigation bar** (desktop and mobile)
- **With cyan glow effect** matching the cyberpunk theme
- **Responsive sizing** for different screen sizes
- **Hover animations** for interactive feel

## 🔧 **Customization Options**

### Change Logo File Name
If you want to use a different filename, update these lines in `index.html`:

```html
<!-- Desktop navigation -->
<img src="images/YOUR_LOGO_NAME.png" alt="LionFish Consultant" class="logo-image">

<!-- Mobile navigation -->
<img src="images/YOUR_LOGO_NAME.png" alt="LionFish Consultant" class="logo-image">
```

### Adjust Logo Size
Modify the CSS in `templatemo-nexus-style.css`:

```css
/* Desktop logo size */
.logo-image {
    height: 40px;  /* Change this value */
    width: auto;
}

/* Mobile logo size */
.mobile-menu-logo .logo-image {
    height: 30px;  /* Change this value */
    width: auto;
}
```

### Change Logo Glow Color
Update the filter property:

```css
.logo-image {
    filter: drop-shadow(0 0 8px var(--primary-cyan)); /* Change color here */
}
```

## 🎯 **Logo Design Tips**

For best results with your cyberpunk LionFish logo:

1. **Transparent background** - PNG format recommended
2. **High resolution** - At least 200x200px
3. **Simple design** - Works well at small sizes
4. **Contrast** - Should be visible against dark backgrounds
5. **Consistent colors** - Matches your brand colors

## ✅ **What's Already Set Up**

- ✅ Logo integration in navigation
- ✅ Responsive sizing for mobile/desktop
- ✅ Glow effects matching the theme
- ✅ Hover animations
- ✅ Proper alt text for accessibility

## 🚀 **Next Steps**

1. **Add your logo file** to the images folder
2. **Test on different devices** to ensure it looks good
3. **Adjust size if needed** using the CSS customization options
4. **Deploy your website** with the new logo

Your LionFish Consultant website now has a professional logo integration that perfectly matches your cyberpunk aesthetic and IT/DevOps/Cybersecurity branding! 🦁⚡ 