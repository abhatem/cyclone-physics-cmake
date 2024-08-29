# Cyclone Physics Engine

This project is an implementation of the Cyclone Physics engine, accompanying the book "Game Physics Engine Design" by Ian Millington. The engine is implemented in C++ and demonstrates various physics concepts through different demos.

## Features

- Rigid body and particle physics.
- Collision detection and response.
- Force generators, including gravity and springs.
- Various demo applications showcasing physics simulations.

## Prerequisites

### Ubuntu

To build the project on Ubuntu, you need to have the following dependencies installed:

```bash
sudo apt-get update
sudo apt-get install build-essential cmake freeglut3-dev
```

### Other Platforms

The project is theoretically cross-platform but has only been tested on Ubuntu. On other platforms, you may need to install equivalent OpenGL/GLUT libraries.

- **Windows**: You might need to install "freeglut" and configure your compiler to link against OpenGL and GLUT.
- **macOS**: Install the required libraries using Homebrew:
  ```bash
  brew install freeglut
  ```

## Building the Project

1. Clone the repository:
    ```bash
    git clone https://github.com/idmillington/cyclone-physics.git
    cd cyclone-physics
    ```

2. Generate the build files using CMake:
    ```bash
    cmake .
    ```

3. Build the project:
    ```bash
    make
    ```

## Running the Demos

Each demo is built as a separate executable. After building, you can run any demo from the command line:

```bash
./ballistic
./bridge
# and so on...
```

## Platform-Specific Notes

- **Ubuntu**: The project has been fully tested on Ubuntu.
- **Windows/macOS**: The project has not been tested on these platforms. Additional setup might be required.

## Contributing

Contributions are welcome! If you test the project on other platforms, please report back with any issues or improvements.

## License

This project is licensed under the MIT License. See the "LICENSE" file for more details.
