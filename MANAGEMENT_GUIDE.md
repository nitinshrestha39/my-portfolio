# Portfolio Management Guide

Your portfolio now uses a **data-driven approach** with JSON files! This means you can add, edit, or delete projects and photos without touching any HTML or JavaScript code.

## 📂 File Structure

```
portfolio/
├── index.html              # Main portfolio page
├── projects.html           # Projects listing (auto-loads from JSON)
├── project-detail.html     # Dynamic project detail page
├── photos.html             # Photos gallery (auto-loads from JSON)
├── css/
│   └── styles.css
├── js/
│   └── script.js
├── data/
│   ├── data.json          # Profile data
│   ├── projects.json      # All projects data
│   └── photos.json        # All photos data
└── README.md
```

## 🎯 Managing Projects

### How Projects Work:
- **Single file to manage:** `data/projects.json`
- **Single detail page:** `project-detail.html` (dynamically loads project data)
- **Projects list:** `projects.html` (auto-fetches from JSON)

### Add a New Project:

Edit `data/projects.json` and add a new object to the `projects` array:

```json
{
  "id": 7,
  "title": "Your Project Title",
  "subtitle": "Short subtitle",
  "description": "Brief description shown on project card (2-3 lines)",
  "fullDescription": "Full detailed description shown on detail page",
  "image": "https://images.unsplash.com/... (fullscreen image URL)",
  "cardImage": "https://images.unsplash.com/... (card thumbnail URL)",
  "technologies": ["Tech1", "Tech2", "Tech3"],
  "features": [
    "Feature 1 - description",
    "Feature 2 - description",
    "Feature 3 - description",
    "Feature 4 - description",
    "Feature 5 - description",
    "Feature 6 - description"
  ],
  "duration": "Time spent on project",
  "client": "Solo Project or Client Name",
  "status": "Completed / In Progress",
  "demoLink": "https://demo-link.com",
  "githubLink": "https://github.com/..."
}
```

### Edit a Project:

Simply update the values in the project object in `data/projects.json`. Changes will reflect immediately when you refresh the page!

### Delete a Project:

Remove the entire project object from the `projects` array in `data/projects.json`.

## 📸 Managing Photos

### How Photos Work:
- **Single file to manage:** `data/photos.json`
- **Single gallery page:** `photos.html` (dynamically loads photos)
- **Filter functionality:** Auto-works based on photo categories

### Add a New Photo:

Edit `data/photos.json` and add to the `photos` array:

```json
{
  "id": 13,
  "title": "Photo Title",
  "src": "https://images.unsplash.com/... (image URL)",
  "category": "nature"  // or travel, people, architecture, etc.
}
```

### Available Categories:
- `all` - Shows all photos
- `nature` - Nature/landscape photos
- `travel` - Travel/vacation photos
- `people` - People/portrait photos
- `architecture` - Architecture/buildings photos

### Edit a Photo:

Update the photo object in `data/photos.json`:

```json
{
  "id": 3,
  "title": "Updated Title",
  "src": "https://new-image-url.com/photo.jpg",
  "category": "travel"
}
```

### Delete a Photo:

Remove the entire photo object from the `photos` array in `data/photos.json`.

## ⚡ How It Works Behind the Scenes

### Projects:
1. `projects.html` fetches `data/projects.json`
2. JavaScript loops through projects and creates cards dynamically
3. Each card links to `project-detail.html?id=X`
4. `project-detail.html` reads the URL parameter and fetches the specific project from JSON
5. Project details are displayed dynamically

### Photos:
1. `photos.html` fetches `data/photos.json`
2. JavaScript renders all photos in a grid
3. Filter buttons let you show photos by category
4. Click any photo to open it full-size in lightbox
5. Photos are fully dynamic - add/remove from JSON and they appear instantly

## 💡 Tips & Best Practices

### Image URLs:
- Use **Unsplash** for free high-quality images: `https://images.unsplash.com/photo-...?w=800&q=60&auto=format&fit=crop`
- You can also use your own hosted images
- Use different URLs for `cardImage` (smaller) and `image` (larger)

### Project IDs:
- IDs must be **unique numbers** (1, 2, 3, 4, 5, 6, 7, etc.)
- Used for linking to detail pages
- Don't skip numbers if possible

### Categories:
- Keep categories **lowercase** (nature, travel, people, architecture)
- Use **consistent spelling**
- Add new categories by creating new filter buttons and updating JSON

### Descriptions:
- `description`: Keep it **short** (2-3 lines) for the card view
- `fullDescription`: Can be **longer** and more detailed for detail page
- `features`: Use format "Feature Name - description" (split by ` - `)

## 🚀 Adding Multiple Projects at Once

You can add multiple projects to `data/projects.json` at once:

```json
{
  "projects": [
    { /* Project 1 */ },
    { /* Project 2 */ },
    { /* Project 3 */ },
    { /* New Project 1 */ },
    { /* New Project 2 */ }
  ]
}
```

Just copy the format of existing projects and paste into the array!

## 🔍 Troubleshooting

### Projects not showing up?
- Check that JSON is valid (use https://jsonlint.com/)
- Ensure all required fields are present
- Check browser console for errors (F12 → Console)

### Lightbox not working?
- Make sure photo image URL is valid
- Check if `data/photos.json` is properly formatted

### Filter buttons not working?
- Verify categories match exactly in `data/photos.json`
- Check that filter buttons have correct `data-filter` attributes

## ✨ No More Code Editing!

You're all set! From now on:
- ✅ Add projects by editing JSON only
- ✅ Add photos by editing JSON only
- ✅ No risk of breaking HTML/CSS/JS code
- ✅ Easy to maintain and scale
- ✅ Can convert to database later if needed

Happy managing! 🎉
