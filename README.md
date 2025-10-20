# Black Hole Physics Simulation - macOS Version

![Black Hole Simulation](https://img.shields.io/badge/Physics-Simulation-blue) ![macOS](https://img.shields.io/badge/Platform-macOS-lightgrey) ![OpenGL](https://img.shields.io/badge/Graphics-OpenGL-green) ![C++](https://img.shields.io/badge/Language-C%2B%2B17-red)

A macOS-compatible real-time black hole physics simulation featuring gravitational lensing, spacetime curvature visualization, and interactive controls.

## 🙏 Original Authors & Credits

**This is a macOS adaptation of the original Windows version. Full credit goes to:**

- **🌟 kavan010 (Kavan)** - [@squee72564](https://github.com/squee72564)
- **🌟 Alexander Rodriguez** - [@CaseyChesshir](https://github.com/CaseyChesshir)
- **🌟 Casey Chesshir** - [@CaseyChesshir](https://github.com/CaseyChesshir)

*Original Project*: Windows-based Black Hole Simulation  
*This Version*: macOS Compatibility Adaptation  

**📺 Original Video Explanation**: [YouTube - Black Hole Simulation Explained](https://www.youtube.com/watch?v=8-B6ryuBkCM)

---

## ✨ Features

### 🌌 Physics Simulation
- **Real-time Black Hole Visualization** - Schwarzschild geometry implementation
- **Gravitational Lensing Effects** - Accurate light ray bending simulation  
- **Spacetime Curvature Grid** - 3D visualization of spacetime warping
- **Interactive Physics Parameters** - Toggle gravity, adjust simulation speed
- **Multiple Rendering Modes** - GPU and CPU-based implementations

### 🍎 macOS Optimizations
- **OpenGL Compatibility** - Adapted from 4.3 to 3.3 Core + Forward Compatible
- **Homebrew Integration** - Easy dependency installation
- **CPU Fallback Mode** - Works on all macOS systems (recommended)
- **Native Build Tools** - CMake + manual clang++ compilation options

## 🚀 Quick Start

### Prerequisites
```bash
# Install dependencies via Homebrew
brew install glew glfw glm cmake
```

### Build & Run

#### Option 1: Manual Compilation (Recommended)
```bash
# CPU version (best macOS compatibility)
clang++ -std=c++17 \
  -I/opt/homebrew/include \
  -L/opt/homebrew/lib \
  -lglfw -lGLEW -framework OpenGL \
  CPU-geodesic.cpp -o cpu_black_hole

# Run simulation
./cpu_black_hole
```

#### Option 2: CMake Build
```bash
mkdir build && cd build
cmake ..
make
./BlackHole3D  # or ./BlackHole2D
```

## 🎮 Controls

| Input | Action |
|-------|--------|
| 🖱️ **Left Mouse Drag** | Orbit camera around black hole |
| 🖱️ **Mouse Wheel** | Zoom in/out |
| 🖱️ **Right Mouse** | Toggle gravity simulation |
| ⌨️ **G Key** | Toggle gravity effects |
| ⌨️ **Space** | Toggle geodesics rendering (CPU version) |

## 📁 Project Structure

```
black-hole-macos/
├── README.md              # This file
├── CMakeLists.txt         # CMake build configuration
├── black_hole.cpp         # Main GPU simulation (requires OpenGL 4.3+)
├── CPU-geodesic.cpp       # CPU-based simulation (macOS recommended)
├── 2D_lensing.cpp         # 2D gravitational lensing effects
├── ray_tracing.cpp        # Ray tracing implementation
├── geodesic.comp          # Compute shader (GPU version)
├── grid.vert              # Grid vertex shader
├── grid.frag              # Grid fragment shader
└── vcpkg.json             # Windows dependency config
```

## 🔧 Technical Details

### macOS-Specific Changes
1. **OpenGL Version**: Modified from 4.3 to 3.3 + `GLFW_OPENGL_FORWARD_COMPAT`
2. **Compute Shader Limitation**: macOS OpenGL 4.1 doesn't support compute shaders
3. **CPU Implementation**: Added robust CPU-based geodesic computation
4. **Dependency Management**: Updated for Homebrew package paths

### Performance Notes
- **CPU Version**: ~8-9 FPS (expected for complex physics)
- **GPU Version**: Limited by macOS OpenGL support
- **Recommended**: Use `CPU-geodesic.cpp` for best compatibility

## 🛠️ Build Troubleshooting

### Common Issues

**1. Library Not Found**
```bash
# Ensure Homebrew paths are correct
export CPPFLAGS="-I/opt/homebrew/include"
export LDFLAGS="-L/opt/homebrew/lib"
```

**2. OpenGL Context Failed**
- Ensure you're running with proper display environment
- Try CPU version if GPU version fails

**3. Permission Issues**
```bash
# macOS may require permission for window creation
# Run from Terminal.app or VS Code terminal
```

## 📊 Platform Comparison

| Feature | Original (Windows) | This Version (macOS) |
|---------|-------------------|----------------------|
| **OpenGL Version** | 4.3 Core | 3.3 Core + Forward Compatible |
| **Compute Shaders** | ✅ GPU Accelerated | ❌ → CPU Fallback |
| **Dependencies** | vcpkg | Homebrew |
| **Build System** | CMake + vcpkg | CMake + clang++ |
| **Performance** | ~15-20 FPS | ~8-9 FPS (CPU mode) |

## 🔬 Physics Implementation

The simulation implements:
- **Schwarzschild Metric** for spacetime curvature
- **Geodesic Integration** for light ray paths
- **Gravitational Time Dilation** effects
- **Event Horizon** visualization
- **Accretion Disk** rendering with realistic physics

## 🎓 Educational Value

Perfect for learning:
- **General Relativity** concepts
- **Computer Graphics** programming
- **Physics Simulation** techniques
- **OpenGL** rendering pipeline
- **Cross-platform** development

## 📄 License

This project maintains the same license as the original. Please refer to the original authors for licensing terms.

## 🤝 Contributing

While this is an adaptation, contributions for macOS improvements are welcome:

1. Fork the repository
2. Create feature branch (`git checkout -b feature/improvement`)
3. Commit changes (`git commit -m 'Add macOS improvement'`)
4. Push to branch (`git push origin feature/improvement`)
5. Create Pull Request

## 🐛 Issues & Support

For macOS-specific issues, please open an issue in this repository.  
For original simulation questions, refer to the original authors' work.

## 📚 Related Resources

- **[Original Project Video](https://www.youtube.com/watch?v=8-B6ryuBkCM)** - Detailed code explanation
- **Einstein's General Relativity** - Theoretical foundation
- **OpenGL Documentation** - Graphics programming reference
- **GLFW/GLEW Documentation** - Window and context management

---

### 🙏 Acknowledgments

Special thanks to the original creators for their incredible work on this physics simulation. This macOS adaptation aims to make their brilliant implementation accessible to Apple users while maintaining full attribution and respect for their original contribution to the physics simulation community.

**Original Windows Version** → **macOS Compatible Version**  
*Bringing black hole physics to every platform!* 🌌