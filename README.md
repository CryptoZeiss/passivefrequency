# A Passive Frequency
### Stereoscopic VR Gallery — Shane, RMIT University

A WebXR-based stereoscopic image gallery. Designed to be viewed in a Meta Quest 3 browser for full stereoscopic VR experience, and accessible as a flat gallery on any desktop browser.

---

## Repository Structure

```
passivefrequency/
  index.html        ← Gallery page
  viewer.html       ← WebXR stereoscopic viewer
  images/           ← Your SBS image files go here
  README.md
```

---

## Adding Images

1. Export your SBS images from ComfyUI as JPG (rename from PNG if needed)
2. Drop them into the `images/` folder
3. Open `index.html` and find the **IMAGE MANIFEST** section
4. Add one entry per image:

```javascript
const images = [
  { src: 'images/your-file.jpg', title: 'Title Here', category: 'Listeners' },
  { src: 'images/another.jpg',   title: 'Another',    category: 'Signalers' },
  // categories: Listeners | Signalers | Watchers
];
```

---

## GitHub Pages Setup

1. Create a new repo named `passivefrequency` on GitHub
2. Push this folder contents to the repo root
3. Go to **Settings → Pages**
4. Set source to `main` branch, `/ (root)`
5. Your gallery will be live at:
   `https://yourusername.github.io/passivefrequency`

---

## Viewing in Meta Quest 3

1. Open the **Meta Quest browser**
2. Navigate to your GitHub Pages URL
3. Click any image to open the viewer
4. Tap **Enter VR** — the browser will request VR permission
5. Accept — the image displays in full stereoscopic 3D

The viewer automatically splits the SBS image and routes the correct half to each eye.

---

## How It Works

Each SBS image contains two views side-by-side (left eye | right eye).

The viewer uses **Three.js + WebXR** to:
- Route the left half of the image to the left eye camera (layer 1)
- Route the right half to the right eye camera (layer 2)
- Show a flat left-eye preview on desktop browsers

---

## Linking from Squarespace

To embed in your artist site, add a button or image link pointing to your GitHub Pages URL. Visitors on a Quest headset can tap the link and go directly into the VR experience.

For a seamless transition, use this URL format for direct image launch:
```
https://yourusername.github.io/passivefrequency/viewer.html?img=images/file.jpg&title=Image+Title
```

---

*Built with Three.js r128 + WebXR Device API*
