# ITOA: Image to ASCII Converter

A web-based tool that converts images into ASCII art, with support for both monochrome and color output. Try it at [itoa.hex.dance](https://itoa.hex.dance)

The code and this readme were generated by Claude 3.5 Sonnet.

## Features

- **Drag & Drop Interface**: Simply drag and drop any image file into the converter
- **Color Support**: Toggle between monochrome and colored ASCII output
- **Size Control**: Adjust output size (Small/Medium/Large) for different levels of detail
- **Save as PNG**: Export your ASCII art as a PNG image
- **Responsive Design**: Works on both desktop and mobile devices
- **File Support**: Handles JPG, PNG, and GIF formats

## How It Works

The conversion process follows these steps:

1. **Image Processing**:
   - Image is loaded and scaled to maintain aspect ratio
   - Canvas API is used to access pixel data
   - Each pixel's RGB values are analyzed

2. **ASCII Conversion**:
   - For monochrome output:
     - Pixel brightness is calculated using luminance formula: `0.299R + 0.587G + 0.114B`
     - Brightness is mapped to ASCII characters: ` .:-=+*#%@` (from darkest to brightest)
   
   - For color output:
     - Same ASCII character mapping is used for consistency
     - Original pixel colors are preserved using inline HTML styling
     - Characters are wrapped in `<span>` tags with RGB color values

3. **Output Generation**:
   - Monochrome: Pure text output with newlines
   - Color: HTML structure with styled spans
   - Font size is dynamically calculated to fit the viewport

## Technical Details

- Built with React and Vite
- Uses HTML Canvas for image processing
- Implements custom drag & drop handling
- Features animated UI elements:
  - Matrix-style upload button
  - CRT-effect save button
  - Glitch effect size toggle
  - Animated favicon
