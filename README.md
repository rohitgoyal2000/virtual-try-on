# 👕 Virtual Try-On using Traditional Computer Vision Techniques

This project implements a simple but effective **Virtual Try-On** system using only **traditional computer vision (CV)** methods — no deep learning involved!

The goal is to realistically overlay a clothing image onto a person image using label masks and clever image processing.

---

## 📸 Input & Output

Given:
- A **person image**
- A **clothing item**
- A **label mask** (indicating body regions)

This pipeline generates:
- An **agnostic version of the person** (without the original clothing)
- A **warped version of the cloth** that fits the body
- A final **blended try-on result**

---

## 🧠 Key Steps

1. **Load Images**
   - Person, cloth, and label images are loaded and resized.

2. **Create Agnostic Person**
   - The region labeled as clothing (`label == 4`) is masked out.

3. **Warp the Cloth**
   - Using **contour detection** and **perspective transform**, the cloth is resized and shaped to fit the person's body.

4. **Blend the Result**
   - Using **seamless cloning** and mask smoothing, the warped cloth is blended onto the person for a natural look.

5. **Visualize**
   - All intermediate and final outputs are visualized side-by-side.
