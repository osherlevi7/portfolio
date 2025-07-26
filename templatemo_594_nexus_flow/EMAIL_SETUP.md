# Email Integration Setup Guide

This guide will help you connect your email to the contact form so you receive inquiries directly.

## 🚀 Option 1: Formspree (Recommended - Easiest)

### Step 1: Create Formspree Account
1. Go to [formspree.io](https://formspree.io)
2. Sign up for a free account
3. Create a new form

### Step 2: Get Your Form ID
1. After creating a form, you'll get a unique ID like `xrgjqkqw`
2. Replace `YOUR_FORMSPREE_ID` in the HTML file with your actual ID

### Step 3: Update the HTML
In `index.html`, find this line:
```html
<form class="contact-form" action="https://formspree.io/f/YOUR_FORMSPREE_ID" method="POST">
```

Replace `YOUR_FORMSPREE_ID` with your actual Formspree ID:
```html
<form class="contact-form" action="https://formspree.io/f/xrgjqkqw" method="POST">
```

### Step 4: Test the Form
1. Open your website
2. Fill out and submit the contact form
3. Check your email - you should receive the inquiry

**✅ Benefits:**
- Free for up to 50 submissions/month
- No server setup required
- Spam protection included
- Works immediately

---

## 🔧 Option 2: Netlify Forms (If Hosting on Netlify)

### Step 1: Add Netlify Attribute
In `index.html`, add the `data-netlify="true"` attribute:
```html
<form class="contact-form" action="https://formspree.io/f/YOUR_FORMSPREE_ID" method="POST" data-netlify="true">
```

### Step 2: Deploy to Netlify
1. Upload your files to Netlify
2. Netlify will automatically detect and handle the form
3. Check your Netlify dashboard for form submissions

---

## 📧 Option 3: EmailJS (Client-Side Email)

### Step 1: Sign Up for EmailJS
1. Go to [emailjs.com](https://emailjs.com)
2. Create an account
3. Set up an email service (Gmail, Outlook, etc.)

### Step 2: Update the JavaScript
Replace the form submission code in `templatemo-nexus-scripts.js`:

```javascript
// Add EmailJS script to HTML head
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>

// Initialize EmailJS
emailjs.init("YOUR_USER_ID");

// Update form submission
contactForm.addEventListener('submit', function(e) {
    e.preventDefault();
    
    const templateParams = {
        from_name: document.getElementById('name').value,
        from_email: document.getElementById('email').value,
        company: document.getElementById('company').value,
        service: document.getElementById('service').value,
        message: document.getElementById('message').value
    };
    
    emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
        .then(function(response) {
            // Success handling
        }, function(error) {
            // Error handling
        });
});
```

---

## 🛠️ Option 4: Custom Backend (Advanced)

### Using PHP (if you have a server)
Create a `process-form.php` file:

```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST['name'];
    $email = $_POST['email'];
    $company = $_POST['company'];
    $service = $_POST['service'];
    $message = $_POST['message'];
    
    $to = "your-email@lionfishconsultant.com";
    $subject = "New Contact Form Submission - $service";
    
    $email_content = "Name: $name\n";
    $email_content .= "Email: $email\n";
    $email_content .= "Company: $company\n";
    $email_content .= "Service: $service\n";
    $email_content .= "Message: $message\n";
    
    $headers = "From: $email";
    
    mail($to, $subject, $email_content, $headers);
    
    header("Location: index.html?success=1");
    exit();
}
?>
```

Then update the form action:
```html
<form class="contact-form" action="process-form.php" method="POST">
```

---

## 📋 Recommended Setup for LionFish Consultant

### For Immediate Use:
1. **Use Formspree** - It's the quickest solution
2. **Set up spam filtering** in your email client
3. **Create email templates** for quick responses

### For Professional Setup:
1. **Use a business email** (your-name@lionfishconsultant.com)
2. **Set up email forwarding** to your preferred email
3. **Configure auto-responders** for immediate acknowledgment

### Email Template for Responses:
```
Subject: Thank you for contacting LionFish Consultant

Dear [Name],

Thank you for reaching out to LionFish Consultant regarding [Service Interest].

We have received your inquiry and will review your requirements. Our team will get back to you within 24 hours with a detailed response.

In the meantime, you can learn more about our services at [your-website].

Best regards,
[Your Name]
LionFish Consultant
IT, DevOps & Cybersecurity Services
```

---

## 🔒 Security Considerations

1. **Spam Protection**: Formspree includes basic spam filtering
2. **Rate Limiting**: Consider implementing rate limiting for production
3. **Data Privacy**: Ensure compliance with GDPR if serving EU clients
4. **Backup**: Set up email forwarding as backup

---

## 🚨 Troubleshooting

### Form Not Sending:
1. Check your Formspree ID is correct
2. Verify your email address in Formspree settings
3. Check browser console for JavaScript errors

### Not Receiving Emails:
1. Check spam/junk folder
2. Verify email address in Formspree dashboard
3. Test with a different email address

### Form Validation Issues:
1. Ensure all required fields are filled
2. Check that email format is valid
3. Verify JavaScript is loading properly

---

## 📞 Support

If you need help setting up email integration:
1. Check Formspree documentation
2. Test with a simple form first
3. Contact your hosting provider for server-side options

**Remember**: The contact form is now ready to capture leads and inquiries for LionFish Consultant's IT, DevOps & Cybersecurity services! 