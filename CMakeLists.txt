cmake_minimum_required(VERSION 3.17)

project(cuda-conan-demo CUDA)
    set(CMAKE_CUDA_STANDARD 17)

    file(GLOB SRC ${PROJECT_SOURCE_DIR}/src/*.cu)
    file(GLOB HEADERS ${PROJECT_SOURCE_DIR}/include/*.cuh ${PROJECT_SOURCE_DIR}/include/*.cuhpp)

    add_executable(${PROJECT_NAME} ${SRC} ${HEADERS})
    target_include_directories(${PROJECT_NAME} PUBLIC "include")
    set_property(TARGET ${PROJECT_NAME} PROPERTY CUDA_ARCHITECTURES "native")
    target_compile_options(${PROJECT_NAME} PRIVATE $<$<AND:$<CONFIG:Debug>,$<COMPILE_LANGUAGE:CUDA>>:-G>)