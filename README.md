# 📘 Inverse Texturing: A Differential Approach Using Physically Based Rendering
### **Master’s Thesis – University of Helsinki (2025)**
**Author:** Bhartrhari Srinivasan  
**Supervisors:** Prof. Lauri Oksanen, Janne Pulkkinen (Remedy Entertainment)

---

## 📝 Overview
This repository contains the implementation accompanying the master’s thesis:

**“Inverse Texturing Problem: A Differential Approach Using Physically Based Rendering.”**

The goal is to reconstruct **physically consistent material maps** — diffuse, roughness, specular albedo, and bump — from a small set of photographs, given a **fixed animation‑ready 3D mesh**.  
Differentiable rendering via **nvdiffrast** and **Kaolin** enables gradient-based optimization of camera, lighting, and texture parameters.

---

## ✨ Key Contributions
- Fully differentiable inverse texturing pipeline  
- Analytic Cook–Torrance BRDF with GGX microfacet model  
- Camera calibration using silhouette masks  
- Multi-light inverse rendering for illumination estimation  
- Texture reconstruction for game-ready assets  

---

## 🏗 Pipeline Summary

### **1. Camera Calibration**
A silhouette mask aligns the mesh projection with the reference image.  
Gradient descent optimizes extrinsics, intrinsics, and field of view.

### **2. Lighting Reconstruction**
Five photos taken with different point-light positions are used to estimate:
- Light positions  
- Intensities  
- Roughness and specular maps (auxiliary)  

### **3. Texture Recovery**
Final optimization infers:
- Diffuse (albedo)  
- Roughness  
- Specular albedo  
- Bump map  

### **4. Physically-Based Shading**
A differentiable Cook–Torrance shader using:
- GGX NDF  
- Smith geometry function  
- Schlick Fresnel approximation  

---

## 🛠 Technologies Used
- Python 3  
- PyTorch  
- NVIDIA Kaolin  
- nvdiffrast  
- NumPy, Pillow, OpenCV  
- Matplotlib  

---


## 📊 Key Results
- Camera error: ~1.78% per pixel  
- Lighting error: ~0.2% per pixel  
- Texture reconstruction error: ~0.6% per pixel  

Textures reconstructed are physically meaningful and suitable for game development workflows.

---

## 🚧 Limitations
- High GPU memory usage  
- Simplified point-light model  
- Minor illumination baked into diffuse map  
- Limited reference views  

---

## 🔭 Future Work
- Environment lighting or differentiable path tracing  
- Multi-resolution texture refinement  
- Neural BRDF or hybrid models  
- Expanded multi-view datasets  

---

## 🤝 Acknowledgments
- Remedy Entertainment  
- Prof. Lauri Oksanen  
- Janne Pulkkinen  
- University of Helsinki  

