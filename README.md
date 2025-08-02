# Vulkan Triangle

A basic Vulkan triangle renderer written in C++ using GLFW.

## Features
- Basic Vulkan setup and initialization
- Colored triangle rendering
- GLFW window management
- Inline GLSL shaders

## Requirements
- Vulkan SDK
- GLFW library
- glslc compiler (for shader compilation)
- C++17 compatible compiler

## Building

### Prerequisites
- Install Vulkan SDK from LunarG
- Install CMake
- Install Visual Studio with C++ support (Windows) or build tools

### Build Steps
```bash
# Create build directory
mkdir build
cd build

# Configure with CMake
cmake ..

# Build (Release configuration)
cmake --build . --config Release
```

### Alternative Manual Compilation

#### Windows
```bash
g++ -std=c++17 main.cpp -lglfw3 -lvulkan-1 -o vulkan_triangle
```

#### Linux
```bash
sudo apt install libglfw3-dev libvulkan-dev vulkan-tools
g++ -std=c++17 main.cpp -lglfw -lvulkan -ldl -lpthread -lX11 -lXxf86vm -lXrandr -lXi -o vulkan_triangle
```

#### macOS
```bash
brew install glfw vulkan-headers vulkan-loader
g++ -std=c++17 main.cpp -lglfw -lvulkan -o vulkan_triangle
```

## Running

### After CMake Build
```bash
# Windows
build\Release\vulkan_triangle.exe

# Linux/macOS
build/vulkan_triangle
```

### After Manual Compilation
```bash
./vulkan_triangle
```

