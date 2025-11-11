# Static Personal Portfolio

This is a fully static personal portfolio built with HTML, CSS, and JavaScript (no frameworks).

Files:
- `index.html` — main page
- `css/styles.css` — styles (Google Font: Poppins)
- `js/script.js` — loads `data/data.json` and adds interactivity
- `data/data.json` — hobbies, likes, dislikes and profile data

Preview locally:

Open `index.html` directly in your browser (works for the basic layout), or start a local server for correct fetch() loading of `data/data.json`:

PowerShell (from project folder):

```powershell
# from inside "c:\Users\nitin\Desktop\lets go\portfolio"
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

Or (Windows PowerShell alternative using PowerShell 3+):

```powershell
Start-Process "http://localhost:8000"
```

License: MIT — adapt content as you like.
