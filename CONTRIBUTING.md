# Contributing to Black Hole Simulation - macOS

Thank you for your interest in contributing to this project! 🌌

## 🙏 Acknowledgment

This project is a macOS adaptation of the original Windows-based Black Hole simulation created by:
- **kavan010 (Kavan)** - [@squee72564](https://github.com/squee72564)
- **Alexander Rodriguez** - [@CaseyChesshir](https://github.com/CaseyChesshir)
- **Casey Chesshir** - [@CaseyChesshir](https://github.com/CaseyChesshir)

All contributions should respect and maintain proper attribution to the original creators.

## 🎯 Types of Contributions

We welcome contributions in several areas:

### 🍎 macOS-Specific Improvements
- Performance optimizations for Apple hardware
- Metal API integration
- Native macOS features integration
- Apple Silicon optimizations

### 🔬 Physics Enhancements
- Additional physics effects
- Improved accuracy of calculations
- New visualization modes
- Educational content improvements

### 🛠️ Technical Improvements
- Code quality improvements
- Build system enhancements
- Documentation improvements
- Bug fixes

### 📚 Educational Content
- Physics explanations
- Tutorial content
- Example projects
- Documentation improvements

## 🚀 Getting Started

### Prerequisites
- macOS 10.14 or later
- Xcode Command Line Tools
- Homebrew
- Git

### Setup Development Environment
```bash
# Clone the repository
git clone https://github.com/1304674612/black-hole-simulation-macos.git
cd black-hole-simulation-macos

# Install dependencies
brew install glew glfw glm cmake

# Test build
clang++ -std=c++17 -I/opt/homebrew/include -L/opt/homebrew/lib \
  -lglfw -lGLEW -framework OpenGL CPU-geodesic.cpp -o cpu_black_hole

# Verify it runs
./cpu_black_hole
```

## 📋 Development Guidelines

### Code Style
- **Language**: C++17
- **Formatting**: Use consistent indentation (4 spaces)
- **Comments**: Document physics concepts and complex algorithms
- **Naming**: Use descriptive variable names

### Physics Accuracy
- Maintain scientific accuracy in all physics implementations
- Document the physics concepts being implemented
- Include references to relevant physics literature when applicable

### macOS Compatibility
- Test on both Intel and Apple Silicon Macs when possible
- Use OpenGL 3.3 Core + Forward Compatible profile
- Provide fallbacks for features not available on macOS

### Performance Considerations
- Profile code changes for performance impact
- Consider both CPU and GPU performance
- Document performance characteristics

## 🔄 Contribution Process

### 1. Fork and Clone
```bash
# Fork the repository on GitHub, then:
git clone https://github.com/YOUR_USERNAME/black-hole-simulation-macos.git
cd black-hole-simulation-macos
git remote add upstream https://github.com/1304674612/black-hole-simulation-macos.git
```

### 2. Create a Feature Branch
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/issue-description
```

### 3. Make Changes
- Follow the coding guidelines
- Add tests if applicable
- Update documentation as needed
- Ensure the project still builds and runs

### 4. Test Your Changes
```bash
# Test manual build
clang++ -std=c++17 -I/opt/homebrew/include -L/opt/homebrew/lib \
  -lglfw -lGLEW -framework OpenGL CPU-geodesic.cpp -o cpu_black_hole

# Test CMake build
mkdir build && cd build
cmake ..
make

# Run and verify functionality
./cpu_black_hole
```

### 5. Commit Your Changes
```bash
git add .
git commit -m "feat: add descriptive commit message

- Detailed description of changes
- Physics concepts involved
- Performance impact if any"
```

### 6. Push and Create Pull Request
```bash
git push origin feature/your-feature-name
```
Then create a Pull Request on GitHub.

## 📝 Commit Message Guidelines

### Format
```
type(scope): short description

Longer description if needed
- Key changes
- Physics concepts involved
- Breaking changes if any
```

### Types
- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Code style changes
- **refactor**: Code refactoring
- **perf**: Performance improvements
- **test**: Test additions/changes

### Examples
```
feat(physics): add gravitational wave visualization

- Implement ripple effects around black hole
- Add time-varying metric perturbations
- Performance impact: ~5% CPU increase

fix(macos): resolve OpenGL context creation on M2 Macs

- Add explicit forward compatibility flag
- Handle Metal-backed OpenGL edge cases
- Fixes issue #15
```

## 🧪 Testing

### Manual Testing Checklist
- [ ] Project builds successfully with clang++
- [ ] Project builds successfully with CMake
- [ ] Application launches without errors
- [ ] All mouse/keyboard controls work
- [ ] Physics simulation runs smoothly
- [ ] No memory leaks or crashes
- [ ] Performance is acceptable

### Platform Testing
- [ ] Intel Mac (if available)
- [ ] Apple Silicon Mac (if available)
- [ ] Different macOS versions (if possible)

## 📚 Resources

### Physics References
- Einstein's General Relativity
- Schwarzschild Metric
- Gravitational Lensing Theory
- [Original Video Explanation](https://www.youtube.com/watch?v=8-B6ryuBkCM)

### Technical References
- [OpenGL Documentation](https://www.opengl.org/documentation/)
- [GLFW Documentation](https://www.glfw.org/documentation.html)
- [GLM Documentation](https://glm.g-truc.net/)

### macOS Development
- [Apple Developer Documentation](https://developer.apple.com/documentation/)
- [Metal API Reference](https://developer.apple.com/metal/)

## 🐛 Reporting Issues

Please use our issue templates:
- [Bug Report](.github/ISSUE_TEMPLATE/bug_report.md)
- [Feature Request](.github/ISSUE_TEMPLATE/feature_request.md)

## 💬 Getting Help

- **Issues**: For bugs and feature requests
- **Discussions**: For general questions and ideas
- **Email**: For private matters (see profile)

## 📄 License

By contributing, you agree that your contributions will be licensed under the same license as the project.

---

**Thank you for helping make black hole physics accessible to macOS users!** 🌌🍎