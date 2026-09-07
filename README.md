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

## 🛠️ Project Structure

```text
├── include/           # Header files for IUP GUI toolkit
├── iup/               # IUP library files
├── bmp.c / bmp.h      # BMP-specific formatting and parsing routines
├── image.c / image.h  # Core Image struct, allocations, loading, saving
├── operations.c / .h  # Image processing operations (filters, transformations)
├── gui.c / gui.h      # IUP Graphical User Interface logic
├── main.c             # Entry point
├── iup.dll            # IUP dynamic link library (Windows runtime)
└── README.md          # Project documentation



💻 Prerequisites & Setup
Requirements
Compiler: gcc (MinGW-w64 / MSYS2 recommended for Windows)

GUI Framework: IUP Toolkit (included in repository)

🔨 Building and Running
Building on Windows (MinGW / GCC)
Because this project utilizes iup.dll for runtime GUI components, compile by linking directly to the DLL or library folder:

PowerShell:
gcc bmp.c gui.c image.c main.c operations.c iup.dll -o imagemanipulation.exe -Iinclude -lgdi32 -lcomctl32 -lcomdlg32 -lole32 -luuid

Note for MSYS2 UCRT64 Users:

If compiling inside an MSYS2 UCRT environment, you can alternatively install IUP natively via pacman -S mingw-w64-ucrt-x86_64-iup and build with:

PowerShell:
gcc bmp.c gui.c image.c main.c operations.c -o imagemanipulation.exe -Iinclude -liup -lgdi32 -lcomctl32 -lcomdlg32 -lole32 -luuid

Running the Application
Execute the compiled executable from your terminal or double-click imagemanipulation.exe:

PowerShell:
.\imagemanipulation.exe

(Ensure iup.dll remains in the same root directory as the .exe file).

📐 BMP Specification Details
The custom reader in image.c manually handles the official Microsoft BMP format specification:

BMPFileHeader (14 bytes): Identifies file type (BM / 0x4D42), total size, and starting byte offset for pixel data.

BMPInfoHeader (40 bytes): Defines width, height, color depth (24-bit), and compression status (0 / BI_RGB).

Pixel Data Layout: Stores colors in BGR byte order rather than RGB. Each scanline is padded with empty bytes up to the nearest multiple of 4.



---

# Image Manipulation Software

A C-based GUI image processing application built using IUP and custom BMP handling routines.

---

### Application Interface

| Main GUI Window |
| :---: |
| ![Main UI](https://raw.githubusercontent.com/FyeizaYusraYusha/imagemanipulation_software/main/screenshot/ui.png) |

---

### File Operations (FILE)

| Image Loaded |
| :---: |
| ![Bitmap Loaded](https://raw.githubusercontent.com/FyeizaYusraYusha/imagemanipulation_software/main/screenshot/bitmap.png) |

---

### Basic Image Adjustments (ADJUSTMENTS)

| Grayscale | Color Inversion |
| :---: | :---: |
| ![Grayscale](https://raw.githubusercontent.com/FyeizaYusraYusha/imagemanipulation_software/main/screenshot/grayscale.png) | ![Invert](https://raw.githubusercontent.com/FyeizaYusraYusha/imagemanipulation_software/main/screenshot/invert.png) |

### 💡 Understanding Rotation vs. Flips

Rotating an image sequentially mirrors specific combinations of horizontal and vertical flips:

* **2 Rotations (180°):** Equivalent to applying both a **Horizontal Flip** and a **Vertical Flip** simultaneously ($Rotate_{180^\circ} = Flip_H \circ Flip_V$).
* **Full Cycle Reversion (360°):** Applying **4 consecutive 90° rotations** completes a full $360^\circ$ circle, restoring the pixel buffer back to its exact **original orientation** ($Rotate_{360^\circ} = Original$).

---

## 🛠️ Project Structure

```text
├── include/           # Header files for IUP GUI toolkit
├── iup/               # IUP library files
├── bmp.c / bmp.h      # BMP-specific formatting and parsing routines
├── image.c / image.h  # Core Image struct, allocations, loading, saving
├── operations.c / .h  # Image processing operations (filters, transformations)
├── gui.c / gui.h      # IUP Graphical User Interface logic
├── main.c             # Entry point
├── iup.dll            # IUP dynamic link library (Windows runtime)
└── README.md          # Project documentation

📜 License
This project is open-source and intended for educational and demonstration purposes.
