# macOS Build Guide

## 🍎 macOS-Specific Instructions

This guide covers the unique aspects of building and running the Black Hole simulation on macOS.

## Prerequisites

### 1. Install Homebrew (if not already installed)
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 2. Install Dependencies
```bash
# Essential OpenGL libraries
brew install glew glfw glm

# Build tools (optional, for CMake build)
brew install cmake
```

### 3. Verify Installation
```bash
# Check if libraries are installed
brew list | grep -E "(glew|glfw|glm)"

# Verify paths (should show library locations)
pkg-config --libs --cflags glfw3
```

## Build Options

### Option 1: Manual Build (Recommended)

#### CPU Version (Best Compatibility)
```bash
clang++ -std=c++17 \
  -I/opt/homebrew/include \
  -L/opt/homebrew/lib \
  -lglfw -lGLEW -framework OpenGL \
  CPU-geodesic.cpp -o cpu_black_hole

# Run
./cpu_black_hole
```

#### GPU Version (Limited by macOS OpenGL 4.1)
```bash
clang++ -std=c++17 \
  -I/opt/homebrew/include \
  -L/opt/homebrew/lib \
  -lglfw -lGLEW -framework OpenGL \
  black_hole.cpp -o black_hole

# Run (may fail due to compute shader requirements)
./black_hole
```

### Option 2: CMake Build
```bash
mkdir build && cd build
cmake ..
make

# Run available executables
./BlackHole3D    # Main 3D version
./BlackHole2D    # 2D lensing version
```

## Troubleshooting

### Common Issues

#### 1. "Library not found" errors
```bash
# If using Intel Mac
export CPPFLAGS="-I/usr/local/include"
export LDFLAGS="-L/usr/local/lib"

# If using Apple Silicon Mac
export CPPFLAGS="-I/opt/homebrew/include"
export LDFLAGS="-L/opt/homebrew/lib"
```

#### 2. "Failed to create GLFW window"
- Ensure you're running from a terminal with display access
- Try running from Terminal.app or VS Code integrated terminal
- Check if you're running via SSH (won't work without X11 forwarding)

#### 3. "Compute shader compile error"
- This is expected on macOS due to OpenGL 4.1 limitation
- Use the CPU version instead: `./cpu_black_hole`

#### 4. Poor Performance
- CPU version runs at ~8-9 FPS (normal for complex physics)
- Close other graphics-intensive applications
- Consider reducing simulation complexity in code

### Hardware Requirements

#### Minimum
- macOS 10.14 or later
- Any Mac with dedicated or integrated graphics
- 4GB RAM

#### Recommended
- macOS 12.0 or later  
- Mac with dedicated GPU (for better performance)
- 8GB RAM

## Performance Optimization

### 1. Compiler Optimizations
```bash
# Add optimization flags
clang++ -std=c++17 -O3 -march=native \
  -I/opt/homebrew/include \
  -L/opt/homebrew/lib \
  -lglfw -lGLEW -framework OpenGL \
  CPU-geodesic.cpp -o cpu_black_hole
```

### 2. System Settings
```bash
# Increase GPU performance (if applicable)
sudo pmset -c gpuswitch 1  # Force discrete GPU

# Verify current GPU
system_profiler SPDisplaysDataType | grep Chipset
```

## Development Setup

### VS Code Configuration
Create `.vscode/c_cpp_properties.json`:
```json
{
    "configurations": [
        {
            "name": "Mac",
            "includePath": [
                "${workspaceFolder}/**",
                "/opt/homebrew/include"
            ],
            "defines": [],
            "macFrameworkPath": [
                "/System/Library/Frameworks",
                "/Library/Frameworks"
            ],
            "compilerPath": "/usr/bin/clang",
            "cStandard": "c17",
            "cppStandard": "c++17",
            "intelliSenseMode": "macos-clang-arm64"
        }
    ],
    "version": 4
}
```

### Build Task
Create `.vscode/tasks.json`:
```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Build CPU Black Hole",
            "type": "shell",
            "command": "clang++",
            "args": [
                "-std=c++17",
                "-I/opt/homebrew/include",
                "-L/opt/homebrew/lib",
                "-lglfw",
                "-lGLEW",
                "-framework", "OpenGL",
                "CPU-geodesic.cpp",
                "-o", "cpu_black_hole"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ]
}
```

## Platform-Specific Notes

### Apple Silicon vs Intel
The build commands work on both, but library paths may differ:

- **Apple Silicon**: `/opt/homebrew/`
- **Intel**: `/usr/local/`

### OpenGL Limitations
macOS OpenGL support is limited to 4.1, which means:
- No compute shaders (requires 4.3+)
- Some advanced features disabled
- CPU fallback is necessary for full functionality

### Metal Alternative
For future versions, consider Metal API for better macOS performance:
```cpp
// Future enhancement idea
#ifdef __APPLE__
    // Use Metal instead of OpenGL compute shaders
#endif
```

## Next Steps

1. **Run the simulation**: Start with CPU version
2. **Experiment with controls**: Mouse and keyboard interactions
3. **Modify physics**: Edit source code to change simulation parameters
4. **Contribute**: Submit macOS-specific improvements

---

*Happy black hole simulation on macOS!* 🌌🍎