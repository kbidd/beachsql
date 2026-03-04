# BeachSQL Website - Setup Guide

## What You Have

A complete, professional company profile website with:
- Responsive design (mobile-friendly)
- Smooth animations and transitions
- Contact form
- Services showcase
- About section with stats
- Professional blue/beach theme

## Files

- `index.html` - Main HTML file
- `styles.css` - All styling
- `script.js` - Interactive features
- `README.md` - This file

---

## How to Point to beachsql.com

### Option 1: Use GitHub Pages (Free & Easy)

1. **Create GitHub Account** (if you don't have one)
   - Go to github.com
   - Sign up for free

2. **Create New Repository**
   - Click "New Repository"
   - Name: `beachsql-website`
   - Make it Public
   - Click "Create repository"

3. **Upload Files**
   - Click "uploading an existing file"
   - Drag and drop: index.html, styles.css, script.js
   - Commit changes

4. **Enable GitHub Pages**
   - Go to Settings → Pages
   - Source: Deploy from main branch
   - Folder: / (root)
   - Save
   - Your site will be at: `https://yourusername.github.io/beachsql-website`

5. **Point Your Domain**
   - In repository, create file named `CNAME`
   - Content: `beachsql.com`
   - Commit the file

6. **Configure DNS** (at your domain registrar)
   - Add these DNS records:
     ```
     Type: A
     Name: @
     Value: 185.199.108.153

     Type: A
     Name: @
     Value: 185.199.109.153

     Type: A
     Name: @
     Value: 185.199.110.153

     Type: A
     Name: @
     Value: 185.199.111.153

     Type: CNAME
     Name: www
     Value: yourusername.github.io
     ```

7. **Wait for DNS** (15 minutes - 48 hours)

---

### Option 2: Use Netlify (Free, Very Easy)

1. **Go to netlify.com**
   - Sign up for free

2. **Drag & Drop**
   - Drag the entire `beachsql-website` folder onto Netlify
   - It will deploy automatically
   - You'll get a URL like: `random-name.netlify.app`

3. **Add Custom Domain**
   - Click "Domain settings"
   - Click "Add custom domain"
   - Enter: `beachsql.com`
   - Netlify will show you DNS records to add

4. **Configure DNS** (at your domain registrar)
   - Add the records Netlify provides (usually):
     ```
     Type: A
     Name: @
     Value: 75.2.60.5

     Type: CNAME
     Name: www
     Value: your-site.netlify.app
     ```

5. **Enable HTTPS**
   - Netlify does this automatically
   - Free SSL certificate

---

### Option 3: Use Vercel (Free, Similar to Netlify)

1. **Go to vercel.com**
   - Sign up with GitHub

2. **Import Project**
   - Click "New Project"
   - Import from GitHub or upload files

3. **Deploy**
   - Vercel deploys automatically

4. **Add Domain**
   - Go to Settings → Domains
   - Add `beachsql.com`
   - Follow DNS instructions

---

### Option 4: Traditional Web Hosting

If you have a web hosting account (GoDaddy, Bluehost, etc.):

1. **Upload Files via FTP**
   - Connect with FileZilla or similar
   - Upload to public_html or www folder

2. **Point Domain**
   - In your domain registrar, set nameservers to your host's nameservers
   - Or add A record pointing to your hosting IP

---

## DNS Configuration Details

You need to configure DNS at wherever you bought beachsql.com (GoDaddy, Namecheap, etc.):

### For GitHub Pages:
```
A     @       185.199.108.153
A     @       185.199.109.153
A     @       185.199.110.153
A     @       185.199.111.153
CNAME www     yourusername.github.io
```

### For Netlify:
```
A     @       75.2.60.5
CNAME www     your-site.netlify.app
```

### For Vercel:
```
A     @       76.76.21.21
CNAME www     cname.vercel-dns.com
```

---

## Recommended: Use Netlify or Vercel

**Why?**
- ✅ Free hosting
- ✅ Automatic HTTPS/SSL
- ✅ Fast CDN (worldwide)
- ✅ Easy updates (just drag & drop new files)
- ✅ Custom domain support
- ✅ No server management needed

---

## Customization

### Change Company Info
Edit `index.html`:
- Line 48-50: Hero title and description
- Line 61-63: About text
- Line 129-131: Contact information

### Change Colors
Edit `styles.css`:
- Line 16: Primary blue color `#0066cc`
- Line 41: Gradient colors
- Search and replace `#0066cc` with your brand color

### Add Logo
Replace the emoji in navigation (line 12 of index.html):
```html
<!-- Current -->
<h1>🏖️ BeachSQL</h1>

<!-- With logo -->
<h1><img src="logo.png" alt="BeachSQL" height="40"> BeachSQL</h1>
```

### Add Real Contact Form
Replace form submission in `script.js` with:
```javascript
fetch('https://formspree.io/f/YOUR_FORM_ID', {
    method: 'POST',
    body: formData,
    headers: {
        'Accept': 'application/json'
    }
}).then(response => {
    if (response.ok) {
        alert('Thank you! We will get back to you soon.');
        this.reset();
    }
});
```

Get free form at: formspree.io

---

## Testing Locally

Open `index.html` in your browser to test before deploying.

Or use Python simple server:
```bash
cd C:\Users\kbiddle\Downloads\beachsql-website
python -m http.server 8000
# Visit: http://localhost:8000
```

---

## Next Steps

1. Choose hosting (Netlify recommended)
2. Upload files
3. Configure DNS at your domain registrar
4. Wait for DNS propagation (15 min - 48 hours)
5. Visit beachsql.com

---

## Support

If you need help:
1. Check DNS propagation: whatsmydns.net
2. Verify DNS records are correct
3. Clear browser cache
4. Wait 24 hours for full propagation

Good luck with your BeachSQL website! 🏖️
