# OpenGL Model Viewer

A 3D model viewer built with C++ and OpenGL. The goal is to load an OBJ model, render it, and let the user orbit around it with a camera.

> **Status: work in progress.** Currently an OpenGL window is created with GLFW and GLAD. Rendering and model loading are being added step by step.

https://github.com/user-attachments/assets/887c9f45-e2af-4a72-8045-02557d29796a

## Planned features

- [x] Window and OpenGL 3.3 Core context (GLFW + GLAD)
- [ ] Hello Triangle (VBO, VAO, shaders)
- [ ] Transformations and camera (model / view / projection)
- [ ] OBJ loading (vertices, faces, normals)
- [ ] Render modes: points, wireframe, solid
- [ ] Basic lighting
- [ ] Orbit camera controlled with the mouse
- [ ] Drag and drop to load a model

## Tech stack

- C++17
- OpenGL 3.3 Core
- [GLFW](https://www.glfw.org/) 3.4 (window, input, context)
- [GLAD](https://glad.dav1d.de/) (OpenGL function loader)
- Visual Studio 2022 (Windows, x64)

## Build instructions (Windows, Visual Studio 2022)

1. Download the **64-bit Windows binaries** of GLFW from glfw.org.
2. Generate GLAD at glad.dav1d.de (Language: C/C++, API gl 3.3, Profile: Core, Generate a loader).
3. Create a folder for libraries, for example `C:\Libs\` with `Include` and `Lib` inside:
   - Copy the `GLFW` header folder, and the `glad` and `KHR` folders into `C:\Libs\Include`.
   - Copy `glfw3.lib` (from `lib-vc2022`) into `C:\Libs\Lib`.
4. Open `OpenGL-Model-Viewer.sln` in Visual Studio, set the platform to **x64**.
5. In the project properties set:
   - VC++ Directories → Include Directories: `C:\Libs\Include`
   - VC++ Directories → Library Directories: `C:\Libs\Lib`
   - Linker → Input → Additional Dependencies: `glfw3.lib;opengl32.lib`
6. Build and run (Ctrl+F5).

## Controls

- `Esc`: close the window

## What I'm learning

This project follows [LearnOpenGL](https://learnopengl.com/) and is my way of understanding the graphics pipeline and the math behind it (vectors, matrices, transformations).
