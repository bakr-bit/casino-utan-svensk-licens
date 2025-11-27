# Casino utan svensk licens - Standalone HTML

This is a standalone HTML version of the casino page, ready to be hosted on the `casino.yatzyregler.com` subdomain.

## Contents

- `index.html` - Single HTML file with all CSS and JavaScript inlined (47KB)
- `images/` - All required images (10 files, ~15MB total)
- `favicon.ico` - Site favicon

## Features

✅ **Self-contained** - All CSS and JavaScript are inlined in the HTML file
✅ **Mobile responsive** - Fully responsive design with working mobile menu
✅ **Interactive** - Mobile menu toggle functionality using vanilla JavaScript
✅ **SEO optimized** - Includes JSON-LD structured data for search engines
✅ **Fast loading** - Single HTML file minimizes HTTP requests

## File Structure

```
casino-standalone/
├── index.html                                    (47KB)
├── favicon.ico                                   (2.2KB)
├── images/
│   ├── bakgrund-header.webp                     (118KB)
│   ├── fredrik-30x30.webp                       (490B)
│   ├── fredrik-48x48.webp                       (906B)
│   ├── fredrik-200x200.webp                     (5.4KB)
│   ├── image1.png                               (373KB)
│   ├── image2.gif                               (12MB) ⚠️
│   ├── image3.png                               (2.4MB)
│   ├── image4.png                               (435KB)
│   └── yatzyregler.com-logga-transparent.webp  (17KB)
└── README.md
```

## Deployment

### Option 1: Upload to Web Server

1. Upload all files to your web server
2. Ensure the directory structure is preserved
3. Point `casino.yatzyregler.com` to the `index.html` file

### Option 2: Static Hosting (Netlify, Vercel, etc.)

1. Drag and drop the entire `casino-standalone` folder
2. Set up custom domain `casino.yatzyregler.com`

### Option 3: GitHub Pages

1. Create a new repository
2. Upload all files
3. Enable GitHub Pages in repository settings
4. Configure custom domain

## Image Optimization Recommendations

⚠️ **IMPORTANT:** The `image2.gif` file is 12MB, which is very large for web delivery.

**Recommended optimizations:**

1. **Convert to video format:**
   ```bash
   ffmpeg -i images/image2.gif -movflags faststart -pix_fmt yuv420p -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" images/image2.mp4
   ```
   This could reduce the size to ~1-2MB

2. **Optimize GIF:**
   ```bash
   gifsicle -O3 --lossy=80 -o images/image2-optimized.gif images/image2.gif
   ```

3. **Convert to WebP animation:**
   ```bash
   gif2webp -q 80 images/image2.gif -o images/image2.webp
   ```

After optimization, update the `src` attribute in `index.html` for image2.

## URLs and Links

All URLs in the HTML are set to:
- External links to main site: `https://www.yatzyregler.com/`
- Self-references: `https://casino.yatzyregler.com/`
- Affiliate links: `https://toptaxfreecasinos.com/`

## Browser Compatibility

✅ Modern browsers (Chrome, Firefox, Safari, Edge)
✅ Mobile browsers (iOS Safari, Chrome Mobile)
✅ IE11+ (with some graceful degradation)

## Testing Checklist

- [ ] Test on desktop browsers
- [ ] Test on mobile devices
- [ ] Verify mobile menu functionality
- [ ] Check all images load correctly
- [ ] Validate HTML (https://validator.w3.org/)
- [ ] Test page speed (https://pagespeed.web.dev/)
- [ ] Verify SEO meta tags
- [ ] Check structured data (https://search.google.com/test/rich-results)

## Performance Notes

- **HTML file size:** 47KB (gzips to ~12KB)
- **Total page size:** ~15MB (mostly due to image2.gif)
- **After image optimization:** Expected ~3-4MB total
- **Fonts:** Loaded from Google Fonts CDN
- **No external dependencies:** Except Google Fonts

## Support

For questions or issues, contact the main site at yatzyregler.com/kontakt

---

**Last updated:** 2025-11-27
**Version:** 1.0
**Generated from:** Next.js build of yatzyregler.com
