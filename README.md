# Linux System Monitor

This project demonstrates object-oriented programming concepts in C++, alongside reading system data from Linux files and displaying formatted outputs in a text-based interface, similar to the `htop` command-line tool.

## Table of Contents
- [Project Overview](#project-overview)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Building and Running the Project](#building-and-running-the-project)
- [Explanation of Files](#explanation-of-files)
- [License](#license)

## Project Overview
The goal of this project is to:
1. Use **Object-Oriented Programming** (OOP) to structure code in C++.
2. Collect and display system metrics (like CPU and memory usage) using data from the Linux `/proc` file system.
3. Display the information in a text-based user interface using the **ncurses** library.

## Project Structure

- `src/main.cpp`: The entry point of the project. It initializes system data collection and starts the ncurses-based display.
- `src/format.cpp` and `include/format.h`: Contains functions for formatting strings, particularly for time representation.
- `src/ncurses_display.cpp` and `include/ncurses_display.h`: Handles the user interface using the ncurses library. It displays CPU, memory, and process information in the terminal.
- `src/linux_parser.cpp` and `include/linux_parser.h`: Reads system and process data from the Linux file system, especially the `/proc` directory.
- `src/system.cpp` and `include/system.h`: Implements a class responsible for gathering and managing overall system data, like total processes, CPU utilization, and uptime.
- `src/process.cpp` and `include/process.h`: Manages data and logic for individual processes, displaying metrics like CPU usage and memory consumption.
- `src/processor.cpp` and `include/processor.h`: Contains logic specific to CPU data collection and processing.

## Dependencies

To run this project, the following dependencies must be installed:

- **Linux OS** (Linux kernel >= 2.6)
- **cmake** >= 3.11.3
- **make** >= 4.1
- **gcc/g++** >= 7.4.0
- **ncurses** (a library for terminal-based GUI):
  - Install ncurses using the following command:
    ```bash
    sudo apt install libncurses5-dev libncursesw5-dev
    ```

## Building and Running the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/linux-system-monitor.git
   cd linux-system-monitor
   ```

2. Create a `build` directory and navigate into it:
   ```bash
   mkdir build
   cd build
   ```

3. Build the project using `cmake` and `make`:
   ```bash
   cmake ..
   make
   ```

4. Run the executable:
   ```bash
   ./monitor
   ```

## Explanation of Files

- **CMakeLists.txt**: Defines the build configurations for the project. `cmake` reads this file to generate makefiles for compiling the project.
- **src/format.cpp**: Contains helper functions for formatting time and strings, making the output more readable.
- **src/ncurses_display.cpp**: Implements the display logic using the ncurses library to show real-time system data in the terminal.
- **src/linux_parser.cpp**: Reads raw system data from Linux's `/proc` file system, providing details like CPU usage, memory, and process statistics.
- **src/system.cpp**: Manages system-wide data like total processes, running processes, and CPU usage.
- **src/process.cpp**: Retrieves and manages data for individual processes, enabling detailed per-process information display.
- **src/processor.cpp**: Dedicated to CPU-related information, calculating real-time CPU utilization.

## Troubleshooting

If you encounter a **Segmentation Fault (core dumped)** error, it is likely due to accessing invalid memory. Consider using `gdb` (GNU Debugger) to trace the error:
```bash
gdb ./monitor
```
