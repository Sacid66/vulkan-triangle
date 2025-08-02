cmake_minimum_required(VERSION 3.16)
project(VulkanTriangle)


find_package(PkgConfig REQUIRED)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


set(VULKAN_SDK_PATH "C:/VulkanSDK/1.4.321.1")
set(VULKAN_INCLUDE_DIRS "${VULKAN_SDK_PATH}/Include")
set(VULKAN_LIBRARIES "${VULKAN_SDK_PATH}/Lib/vulkan-1.lib")

add_executable(${PROJECT_NAME} main.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE 
    ${VULKAN_INCLUDE_DIRS}
    ${GLFW3_INCLUDE_DIRS}
)


pkg_check_modules(GLFW3 REQUIRED glfw3)

target_link_libraries(${PROJECT_NAME} 
    ${VULKAN_LIBRARIES}
    ${GLFW3_LIBRARIES}
)

if(WIN32)
    target_compile_definitions(${PROJECT_NAME} PRIVATE VK_USE_PLATFORM_WIN32_KHR _AMD64_)
endif()
