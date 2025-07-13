Project template for cross-platform C library.

```bash
# We will use Conan to install external dependencies and generate the files that CMake needs to find this library and build our project
conan install . --output-folder=build --build=missing

cd build

# build on linux:
cmake .. -G "Unix Makefiles" -DCMAKE_TOOLCHAIN_FILE="conan_toolchain.cmake" -DCMAKE_BUILD_TYPE=Release
cmake --build .

# build on windows:
cmake .. -G "Visual Studio 17 2022" -DCMAKE_TOOLCHAIN_FILE="conan_toolchain.cmake"
cmake --build . --config Release
```

There is example of the executable application project in the example/ subfolder.
See example/README.md.
