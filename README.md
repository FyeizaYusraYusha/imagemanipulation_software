# 🖼️ C Image Manipulation & IUP GUI Tool

A lightweight, high-performance image manipulation program written in pure C. This project features a custom, from-scratch 24-bit uncompressed BMP reader/writer, memory-safe pixel operations, and a desktop user interface built using the IUP GUI toolkit.

---

## 🚀 Features

* **Custom BMP Reader & Writer:**
  * Reads and writes uncompressed 24-bit (`BI_RGB`) BMP files without using external image processing libraries.
  * Correctly handles scanline alignment (4-byte row padding).
  * Automatically normalizes top-down (negative height) and bottom-up (positive height) BMP orientation conventions.
* **Core Image Processing Engine:**
  * Dynamic memory management using a contiguous 1D pixel buffer.
  * Built-in bounds and integer-overflow protections for safe memory allocations.
  * Modular design (`operations.c`) for extending image filters and transformations.
* **Graphical User Interface (IUP):**
  * Native desktop interface built with the IUP GUI toolkit.
  * Load, manipulate, and save BMP images interactively.

---

## 💻 Getting Started

### Prerequisites
Make sure you have a C compiler (GCC/MinGW or MSVC) and the **IUP GUI toolkit** configured on your system.

* **GCC / MinGW** (for Windows/Linux)
* **IUP Library** (headers and binary distribution included in `/include` and `/iup`)

---

## 🛠️ How to Build and Run

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/FyeizaYusraYusha/imagemanipulation_software.git](https://github.com/FyeizaYusraYusha/imagemanipulation_software.git)
   cd imagemanipulation_software

---

### Application Interface

| Main GUI Window |
| :---: |
| ![Main UI](./screenshot/ui.png) |

---

### File Operations (FILE)

| Image Loaded |
| :---: |
| ![Bitmap Loaded](./screenshot/bitmap.png) |

---

### Basic Image Adjustments (ADJUSTMENTS)

| Grayscale | Color Inversion |
| :---: | :---: |
| ![Grayscale](./screenshot/grayscale.png) | ![Invert](./screenshot/invert.png) |

| Brightness (Increase) | Brightness (Decrease) |
| :---: | :---: |
| ![Brightness 1](./screenshot/brightness1.png) | ![Brightness 2](./screenshot/brightness2.png) |

| Blur Filter | Sharpen Filter |
| :---: | :---: |
| ![Blur](./screenshot/blur.png) | ![Sharpen](./screenshot/sharpen.png) |

---

### Transformations & Editing (TRANSFORM)

| Horizontal Flip | Vertical Flip |
| :---: | :---: |
| ![Horizontal Flip](./screenshot/hflip.png) | ![Vertical Flip](./screenshot/vflip.png) |

| Image Rotation | History & Undo |
| :---: | :---: |
| ![Rotate](./screenshot/rotate.png) | ![Undo Action](./screenshot/undo.png) |

| Crop Selection | Cropped Output |
| :---: | :---: |
| ![Crop Selection](./screenshot/crop1.png) | ![Crop Result](./screenshot/crop2.png) |
