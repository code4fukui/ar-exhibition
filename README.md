# ar-exhibition

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

> DATA: [神山まるごと高専 学生](https://kamiyama-marugoto.com/) (Students of Kamiyama Marugoto Kosen)

A simple web-based AR application for creating a virtual art exhibition. This project uses Three.js and `egxr.js` to display a series of images on 3D planes, viewable in an augmented reality environment or on a standard desktop browser.

**[View Demo](https://code4fukui.github.io/ar-exhibition/)**

## Features

-   **WebXR-Powered AR:** View the image gallery in your physical space using a compatible AR device.
-   **Desktop Fallback:** Includes first-person controls (mouse-look and keyboard navigation) for standard desktop browsers.
-   **Dynamic Image Loading:** Loads and displays images from a configurable list onto 3D planes.
-   **Adjustable 3D Lighting:** Simple and effective lighting setup using ambient and directional lights.

## How to Use

To run this project locally, you need a local web server to avoid CORS issues.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/code4fukui/ar-exhibition.git
    cd ar-exhibition
    ```

2.  **Start a local server:**
    If you have Python 3, you can use:
    ```bash
    python3 -m http.server
    ```

3.  **Open in your browser:**
    Navigate to `http://localhost:8000` in a WebXR-compatible browser like Chrome or Firefox.

## Customization

You can display your own images by editing the `imgs` array in `index.html`. Each object in the array defines a picture to be displayed:

-   `fn`: The path to the image file.
-   `height`: The height of the image plane in the 3D scene. The width is calculated automatically to maintain the aspect ratio.
-   `text`: A descriptive text string (metadata).

```javascript
// in index.html
const imgs = [
  { fn: "./img1.jpg", height: .32, text: "意味のないツイテール" },
  { fn: "./img2.jpg", height: .41, text: "できかけのショートケーキ" },
  { fn: "./img3.png", height: .41, text: "幸福の証明は、幸福の中で不幸に鳴ること" },
  // Add your own images here
];
```

The images included are:
-   `img1.jpg`: A hand-painted avatar.
-   `img2.jpg`: An abstract placeholder image.
-   `img3.png`: Conceptual artwork with Japanese text.

## Dependencies

This project is built with several open-source libraries:

-   [three.js](https://code4fukui.github.io/three.js/): A 3D graphics library for JavaScript.
-   [egxr.js](https://code4fukui.github.io/egxr.js/): A wrapper for Three.js to simplify WebXR development.
-   [PCControl.js](https://code4fukui.github.io/vr-beetle/PCControl.js): A module for first-person desktop controls.
-   [loadTexture.js](https://code4fukui.github.io/ar-wall/loadTexture.js): A utility for loading textures.

## License

This project is available under the MIT License.

---
[Source on GitHub](https://github.com/code4fukui/ar-exhibition/)