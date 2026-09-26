# HEIC to JPG Studio

A fast, private, browser-based converter for HEIC and HEIF images. The application runs entirely in the browser. Images are decoded, resized, and converted locally using WebAssembly (`heic-to`) and the Canvas API.

**Created by [n1s4t](https://github.com/n1s4t)**

---

## Overview

HEIC and HEIF are commonly used by Apple devices but are not supported by some Windows applications, websites, and older image-editing software. HEIC to JPG Studio provides a simple way to convert these images into widely supported formats without uploading them to a server.

The application is designed for users who need to:

- Convert HEIC and HEIF images to common formats
- Convert multiple images at the same time
- Reduce image dimensions and file size
- Download converted images individually or as a ZIP archive
- Process personal images without sending them to an external server

## Features

### Conversion

- Drag and drop or select multiple HEIC/HEIF files
- Automatically filters unsupported file types
- Convert images to **JPG, PNG, or WebP**
- Adjust image quality from **50% to 100%** for supported formats
- Select a maximum image dimension or keep the original size
- Choose how converted files are named
- Process up to **3 files in parallel**
- Cancel an active conversion
- Retry only the files that failed

### File Management

- Preview each image before conversion
- View the current status of every file
- Display image resolution and output file size
- Download individual converted files
- Download all successful conversions as a ZIP archive
- Remove individual files from the conversion queue
- Clear the entire queue

### Interface

- Light and dark theme support
- Uses the system theme by default
- Remembers selected theme and conversion settings
- Responsive design for desktop and mobile devices
- Keyboard-accessible controls
- Screen-reader-friendly status information

### Privacy

- Image processing is performed locally in the browser
- Image files are not uploaded to an application server
- No account is required
- No server-side image storage is used
- Only user preferences are stored locally in the browser

## Privacy and Security

The converter does not send image data to a conversion server. HEIC decoding, resizing, and output generation take place on the user's device.

The application may load its required JavaScript libraries from a CDN. This means an internet connection may be required when the libraries are not already available in the browser cache.

Converted files do not currently preserve the original EXIF metadata.

## Known Limitations

- EXIF metadata such as camera information, GPS data, and original capture time is not preserved.
- Very large batches or high-resolution images may require significant system memory and processing power.
- A modern browser with WebAssembly and Canvas support is required.
- The application currently depends on externally hosted libraries for HEIC decoding and ZIP creation.

## Technology Stack

- **HTML5**
- **CSS3**
- **Vanilla JavaScript**
- [`heic-to`](https://github.com/hoppergee/heic-to) — HEIC/HEIF decoding
- [`JSZip`](https://stuk.github.io/jszip/) — ZIP archive generation
- **WebAssembly** — HEIC/HEIF decoding
- **Canvas API** — image resizing and encoding

No build system or framework is required.

## Usage

1. Open `heic-to-jpg-studio.html` in a modern web browser.
2. Drag HEIC/HEIF files into the upload area or select them using the file picker.
3. Select the required output format and conversion settings.
4. Click **Convert All**.
5. Download individual files or use **Download ZIP** for the complete batch.

## Supported Output Formats

| Format | Quality Control | Transparency |
|---|---|---|
| JPG | Yes | No |
| PNG | No, lossless | Yes |
| WebP | Yes | Yes |

## Project Structure

```text
HEIC-JPG-Studio/
├── heic-to-jpg-studio.html
└── README.md
```

## Running Locally

No Node.js, npm, Python, or build process is required.

Open:

```text
heic-to-jpg-studio.html
```

in a modern browser such as Chrome, Edge, Firefox, or Safari.

An internet connection may be required on the first run to load the required external libraries.

## Troubleshooting

### Conversion fails

Try the following:

1. Confirm that the selected file is a valid HEIC or HEIF image.
2. Refresh the page and try again.
3. Check your internet connection.
4. Use the latest version of Chrome, Edge, Firefox, or Safari.
5. Try converting a single file.
6. Verify that the original image can be opened on another device.

### Images do not appear in the preview

Refresh the page and try again. The HEIC decoder must load before the browser can display the preview.

### The application does not load correctly

Make sure your network or browser is not blocking:

```text
cdn.jsdelivr.net
```

The application currently uses CDN-hosted libraries.

## Future Improvements

Possible future improvements include:

- Fully offline operation
- Native Windows and macOS applications
- Folder selection and batch folder processing
- Output folder selection
- EXIF metadata preservation
- Automatic image orientation correction
- Before-and-after image comparison
- Custom width and height controls
- Additional image formats
- Improved conversion performance
- Additional language support

## License

This project is provided for personal and development use.

Third-party libraries are distributed under their respective licenses.

---

**HEIC to JPG Studio**  
Browser-based image conversion with local processing and privacy in mind.
