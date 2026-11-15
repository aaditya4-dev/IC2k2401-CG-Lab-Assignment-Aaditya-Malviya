# Computer Graphics & Multimedia Lab Assignments

Practical lab assignments for the **Computer Graphics & Multimedia (CGM)** course (MCA 5 Years).

---

## 👨‍🎓 Student Details

- **Student Name:** Aaditya Malviya  
- **Roll Number:** IC-2K24-01  
- **Course:** MCA (5 Years)  
- **Subject:** Computer Graphics & Multimedia  

---

## 📑 Table of Contents

1. [Assignment 1: Basic Graphics Primitives](#assignment-1-basic-graphics-primitives)
2. [Assignment 2: Digital Differential Analyzer (DDA) Line Generation Algorithm](#assignment-2-digital-differential-analyzer-dda-line-generation-algorithm)
3. [Compilation and Execution Guide](#compilation-and-execution-guide)

---

## Assignment 1: Basic Graphics Primitives

### 🎯 Objective
To write a C++ program using the `graphics.h` library to draw basic graphics primitives in a single graphics window:
1. **Straight Line** using `line()`
2. **Circle** using `circle()`
3. **Rectangle** using `rectangle()`
4. **Triangle** using interconnected `line()` segments

### 💻 Source Code
- **File:** [`CGM_lab1.cpp`](CGM_lab1.cpp)

### 🖼️ Output
<p align="center">
  <img src="Screenshot%202026-09-29%20192412.png" alt="Basic Graphics Primitives Output" width="650"/>
</p>

---

## Assignment 2: Digital Differential Analyzer (DDA) Line Generation Algorithm

### 🎯 Objective
To implement the **Digital Differential Analyzer (DDA)** line generation algorithm in C++ using the `graphics.h` library to calculate and render pixel coordinates between two arbitrary endpoints $(x_1, y_1)$ and $(x_2, y_2)$.

### 📐 Algorithm Overview
The DDA algorithm calculates pixel positions along a straight line by taking unit steps in one coordinate and generating corresponding fractional increments in the other:

1. **Input Endpoints:** Take $(x_1, y_1)$ and $(x_2, y_2)$ as inputs.
2. **Calculate Differentials:**
   $$\Delta x = x_2 - x_1$$
   $$\Delta y = y_2 - y_1$$
3. **Determine Number of Steps:**
   $$\text{steps} = \max(|\Delta x|, |\Delta y|)$$
4. **Calculate Increments:**
   $$x_{\text{inc}} = \frac{\Delta x}{\text{steps}}$$
   $$y_{\text{inc}} = \frac{\Delta y}{\text{steps}}$$
5. **Plot Points:** Successive coordinates are computed iteratively and plotted using `putpixel()`, shifted relative to the screen center $(320 + \text{round}(x), 240 - \text{round}(y))$:
   $$x_{k+1} = x_k + x_{\text{inc}}$$
   $$y_{k+1} = y_k + y_{\text{inc}}$$

### 💻 Source Code
- **File:** [`CGM_lab2.cpp`](CGM_lab2.cpp)

### 🖼️ Output
<p align="center">
  <img src="dda_output.png" alt="DDA Line Generation Algorithm Output" width="650"/>
</p>

---

## 🛠️ Compilation and Execution Guide

### Prerequisites
- GCC / MinGW with 32-bit `graphics.h` and `libbgi.a` support
- Windows Operating System

### Build Commands
Compile with the required WinBGIm graphics and GDI libraries:

```bash
# Assignment 1: Basic Shapes
g++ CGM_lab1.cpp -o CGM_lab1.exe -lbgi -lgdi32 -lcomdlg32 -luuid -loleaut32 -lole32

# Assignment 2: DDA Line Drawing
g++ CGM_lab2.cpp -o CGM_lab2.exe -lbgi -lgdi32 -lcomdlg32 -luuid -loleaut32 -lole32
```
