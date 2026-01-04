# Image Optimization Guide

## Current Status
- OG image: `images/og-image.jpg` (1200x630, PLACEHOLDER - replace with branded image)
- No `<img>` tags currently in use - site is text/CSS only

## When Adding Images

### 1. Lazy Loading (Native Browser)
```html
<img src="image.jpg" alt="Description" loading="lazy" />
```

### 2. Responsive Images with srcset
```html
<img 
  src="image-800.jpg"
  srcset="image-400.jpg 400w, image-800.jpg 800w, image-1200.jpg 1200w"
  sizes="(max-width: 600px) 400px, (max-width: 1000px) 800px, 1200px"
  alt="Description"
  loading="lazy"
/>
```

### 3. WebP with Fallback
```html
<picture>
  <source srcset="image.webp" type="image/webp" />
  <img src="image.jpg" alt="Description" loading="lazy" />
</picture>
```

### 4. Convert to WebP (using ImageMagick)
```bash
magick input.jpg -quality 80 output.webp
```

### 5. Generate Multiple Sizes
```bash
for size in 400 800 1200; do
  magick input.jpg -resize ${size}x output-${size}.jpg
done
```

## Cleanup Done
Removed unused HTML5 UP template images (gallery/*, pic*.jpg, first.png, second.png).
