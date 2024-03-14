# Microros-stm32
This project aim to enable the comunication between ROS2 and STM32 boards using micro-ros. You can choose to use the code in the repository or to build it from scratch. The project was tested on a NUCLEO board but it should work on others board too

## Setup using the repository
If you want to speedup the process you can directly use the code in this repository:
1. Clone this repository in your STM32CubeIDE workspace folder
2. Go to the Library Installation section

## Setup from scratch

## Library Linux
This library installation section will follow what is written in the official micro-ROS for STM32 page, if you want go more in detail or want to install it using Windows follow [this guide](https://github.com/micro-ROS/micro_ros_stm32cubemx_utils/tree/humble)
1. Open this project folder and run
   ```git clone --branch humble https://github.com/micro-ROS/micro_ros_stm32cubemx_utils.git```
2. Go to `d` and in `d` add ``
3. Add micro-ROS include directory. In `Project -> Settings -> C/C++ Build -> Settings -> Tool Settings Tab -> MCU GCC Compiler -> Include paths` add `../micro_ros_stm32cubemx_utils/microros_static_library_ide/libmicroros/include` 
4. Add the micro-ROS precompiled library. In `Project -> Settings -> C/C++ Build -> Settings -> MCU GCC Linker -> Libraries`
   * Add `../micro_ros_stm32cubemx_utils/microros_static_library_ide/libmicroros` in `Library search path (-L)`
   * Add `microros` in `Libraries(-l)`
5. Add the following source code files to your project, dragging them to source folder:
   * `extra_sources/microros_time.c`
   * `extra_sources/microros_allocators.c`
   * `extra_sources/custom_memory_manager.c`
   * `extra_sources/microros_transports/dma_transport.c` or your transport selection
6. Build and run the project 
