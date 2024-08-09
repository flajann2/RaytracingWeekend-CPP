# See https://www.kitware.com/import-cmake-c20-modules/ for how it was done

# Note there are some issues with header units in cmake.
# https://gitlab.kitware.com/cmake/cmake/-/issues/24616

# There is also anothe issue with clang's module support
# https://github.com/llvm/llvm-project/issues/62707
# https://github.com/Kitware/CMake/commit/7b05724ac81c3262ce8aded5578326ecec327ae4


add_library(RayTracingLib)
target_sources(RayTracingLib
  PUBLIC
    FILE_SET cxx_modules TYPE CXX_MODULES FILES
    RaytracingLib/algebra.cppm
    RaytracingLib/camera.cppm
    RaytracingLib/color.cppm
    RaytracingLib/hittable.cppm
    RaytracingLib/images.cppm
    RaytracingLib/material.cppm
    RaytracingLib/ray.cppm
    RaytracingLib/RaytracingLib.cppm
    RaytracingLib/scene.cppm
    RaytracingLib/sphere.cppm
)

add_executable(RayTracing Raytracing/main.cpp)
target_link_libraries(RayTracing PRIVATE RayTracingLib)
