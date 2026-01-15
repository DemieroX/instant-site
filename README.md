# Instant Site 🍜
Static HTML template that turns into a complete personal website. No build tools, no framework setup, no headaches. Edit a JSON file, write some markdown, and you're done.

## Quick Start

1. Download entire repository or replicate this file structure:
```
your-site/
├── index.html
├── content/
│   ├── profile.json
│   ├── homepage.md
│   ├── avatar.jpg
│   ├── banner.jpg
│   ├── blog/
│   │   └── post-x.md (Add any number of posts)
│   ├── gallery.md
│   └── tabs/
│       └── tab-1.md
```

2. Edit `content/profile.json` with your info
3. Write your content in markdown files
4. Open `index.html` in a browser

**That's it!** No npm install, no build process, nothing else :D

## How to Configure
Everything is controlled by `content/profile.json`. Here's what each field does:

### Basic Info
- `name` - Your name/nickname/username
- `status` - Tagline below your name, could be your status like "Studying" or "Working at ..."
- `bio` - Short paragraph about you, tell the world who you are!
- `details` - Array of text/links shown below bio ranging from solid text or text with hyperlink(separated by dots)

Example `detail` with link:
```json
{
  "text": "GitHub",
  "url": "https://github.com/yourusername"
}
```

### Visual Assets
- `avatar` - Your profile picture (square image recommended)
- `banner` - Profile banner image (no image will result in no banner)
- `background` - Optional full-page background image (If there is no image, `gMain` will be used.)

### Theme Colors
- `primary` - Main text color
- `secondary` - Subtitles, captions, secondary text
- `accent` - Links and interactive elements
- `bgMain` - Page background (If there is no background image)
- `bgCard` - Card backgrounds
- `bgSubtle` - Content area backgrounds
- `border` - Border colors
- `font` - Font family (with fallbacks)

### Badges
Colored labels/tags that are under your name:
```json
{
  "label": "Developer",
  "bg": "#0c4a6e",
  "text": "#7dd3fc"
}
```

### Sidebar Cards
Info boxes in the left sidebar for adding small groups of detail:
```json
{
  "title": "Interests",
  "content": "Game Dev · Design · Coffee",
  "bg": "#547256",
  "text": "#E1FFD8",
  "border": "#1B1C1B"
}
```

### Content Files
- `homepageFile` - Path to homepage markdown (default: `content/homepage.md`)
- `galleryFile` - Path to gallery list (default: `content/gallery.md`)
- `blogPosts` - Array of blog post file paths (in display order)

### Custom Tabs
Add extra pages to navigation:
```json
{
  "id": "projects",
  "label": "Projects",
  "file": "content/tabs/projects.md"
}
```

If you omit `file`, it looks for `content/tabs/{id}.md` automatically.

## Writing Content

### Blog Posts
Create markdown files in `content/blog/`. First `# heading` becomes the title.

List them in `profile.json` in the order you want (first = newest):

**THIS SECTION IS IMPORTANT! WITHOUT PROVIDING THE PATH OF BLOG POSTS, THE WEBSITE WILL NOT USE YOUR POSTS!**
```json
"blogPosts": [
  "content/blog/latest-post.md",
  "content/blog/older-post.md"
]
```

### Gallery
Create `content/gallery.md` with one image per line:
```
https://example.com/image1.jpg | Optional caption
https://example.com/image2.jpg | Another caption
path/to/local/image.jpg
```

### Homepage
Write whatever you want in `content/homepage.md`. It shows up on the home page along with your 3 most recent blog posts.

## Features
- **Automatic navigation** - Blog, Gallery, and custom tabs appear based on your content
- **Search** - Built-in search for blog posts
- **Pagination** - Automatic pagination for blogs (10 per page) and gallery (12 per page)
- **Mobile responsive** - Works on most screen sizes
- **No dependencies** - Just one HTML file :)

## Deployment
Since it's just static files, host it anywhere:
- GitHub Pages
- Netlify
- Vercel
- Any web server!
