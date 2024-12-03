# cuda-conan-cmake
Small demo repository that combines Cuda, CMake and Conan together. Example from Nvidia's introduction blog post: https://developer.nvidia.com/blog/easy-introduction-cuda-c-and-c/

## Linux setup
### Pre-requisites
- Install the Cuda SDK
- Install Conan and required Python
- Install VSCode, the NSight for VSCode extension and the CMake extension

### Project Setup
- Clone the repository
- Run `conan install . -of build`
- Open the repository in VSCode
- Use the CMake extension to configure and build the project

### Debugging
- To debug the project create a `.vscode` folder and add a `launch.json` file in that folder
- Use VSCodes launch options to add a `Cuda Launch` target and point it to the built application
