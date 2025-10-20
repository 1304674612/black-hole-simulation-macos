# Release Notes

## v1.0.0-macos (2025-10-20)

### 🌌 Initial Release - Black Hole Physics Simulation for macOS

This is the first stable release of the macOS-compatible Black Hole Physics Simulation, adapted from the original Windows version.

### ✨ Features

- **Real-time Black Hole Visualization** - Experience Schwarzschild geometry in action
- **Gravitational Lensing Effects** - Watch light bend around massive objects
- **Interactive Controls** - Mouse and keyboard interaction for exploration
- **Cross-Platform Compatibility** - Optimized specifically for macOS systems
- **Educational Value** - Perfect for physics education and visualization

### 🍎 macOS Optimizations

- **OpenGL 3.3 Compatibility** - Adapted from OpenGL 4.3 for macOS support
- **CPU-Based Computation** - Robust fallback for compute shader limitations
- **Homebrew Integration** - Easy dependency installation via `brew`
- **Forward Compatibility** - Uses `GLFW_OPENGL_FORWARD_COMPAT` for future macOS versions

### 🙏 Original Authors

- **kavan010 (Kavan)** - [@squee72564](https://github.com/squee72564)
- **Alexander Rodriguez** - [@CaseyChesshir](https://github.com/CaseyChesshir)
- **Casey Chesshir** - [@CaseyChesshir](https://github.com/CaseyChesshir)

### 📥 Installation

#### Quick Start
```bash
# Install dependencies
brew install glew glfw glm

# Build and run CPU version (recommended)
clang++ -std=c++17 -I/opt/homebrew/include -L/opt/homebrew/lib \
  -lglfw -lGLEW -framework OpenGL CPU-geodesic.cpp -o cpu_black_hole
./cpu_black_hole
```

#### CMake Build
```bash
mkdir build && cd build
cmake ..
make
./BlackHole3D
```

### 🎮 Controls

| Input | Action |
|-------|--------|
| Left Mouse Drag | Orbit camera around black hole |
| Mouse Wheel | Zoom in/out |
| Right Mouse | Toggle gravity simulation |
| G Key | Toggle gravity effects |
| Space | Toggle geodesics rendering |

### 📊 Performance

- **CPU Version**: ~8-9 FPS (stable, recommended)
- **GPU Version**: Limited by macOS OpenGL 4.1
- **Memory Usage**: ~50-100MB
- **Compatibility**: macOS 10.14+ (tested on macOS 12+)

### 🔧 Technical Details

- **Language**: C++17
- **Graphics API**: OpenGL 3.3 Core + Forward Compatible
- **Dependencies**: GLEW, GLFW, GLM
- **Build System**: CMake + manual clang++
- **Physics**: Schwarzschild metric implementation

### 📚 Educational Resources

- **Original Video**: [Black Hole Simulation Explained](https://www.youtube.com/watch?v=8-B6ryuBkCM)
- **Physics Concepts**: General Relativity, Gravitational Lensing, Event Horizons
- **Programming Concepts**: OpenGL, Physics Simulation, Real-time Rendering

### 🐛 Known Issues

- GPU version may fail on some macOS systems due to compute shader limitations
- Performance varies based on GPU capabilities
- Some visual artifacts possible on integrated graphics

### 🔮 Future Plans

- [ ] Metal API integration for better macOS performance
- [ ] Additional physics parameters
- [ ] VR support exploration
- [ ] Performance optimizations
- [ ] More educational content

---

**Download**: See [Releases](https://github.com/1304674612/black-hole-simulation-macos/releases)  
**Issues**: [Report bugs or request features](https://github.com/1304674612/black-hole-simulation-macos/issues)  
**Contributing**: See [Contributing Guidelines](CONTRIBUTING.md)