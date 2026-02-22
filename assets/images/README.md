# Images Directory

This directory contains images used throughout the blog.

## Structure

- `/posts/` - Images used in blog posts
- Root level - Site-wide images (logo, favicon, etc.)

## Usage in Posts

### Basic Image
```markdown
![Alt text](/assets/images/posts/your-image.png)
```

### Image with Caption
```markdown
![Alt text](/assets/images/posts/your-image.png)
*Caption text goes here*
```

## Best Practices

1. **Naming Convention**: Use descriptive, kebab-case names
   - Good: `architecture-diagram-v2.png`
   - Bad: `IMG_1234.png`

2. **Organization**: Store post images in `/posts/` subdirectory
   - Optionally create subfolders per post: `/posts/2026-02-08-post-name/`

3. **File Formats**:
   - Use PNG for diagrams, screenshots, images with transparency
   - Use JPG for photos
   - Use WebP for optimized images (when supported)
   - Use SVG for icons and simple graphics

4. **File Size**: Optimize images before uploading
   - Aim for under 500KB per image
   - Use tools like ImageOptim, TinyPNG, or squoosh.app

5. **Accessibility**: Always include descriptive alt text
