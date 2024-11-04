# Lecture 2

Digital inputs with Rpi pico and C/C++ SDK.

## File Structure

- `main.c` : C source file (sample 'led on button' program)
- `CMakeLists.txt`: Cmake build configuration

## Assignment

Using the pico-sdk documentation, online resources, and pico-sdk examples, research how to use interrupts and handle digital signals with the pico-sdk. Your task is to write a program that uses two buttons to function as a counter. One button should increment the counter, and the other should decrement it. The counter value should be printed in place using `\r` for better display.

### Pseudocode for Button Counter

1. Define the pins for the buttons.
2. Initialize the pins for input.
3. Set up interrupts for the button pins.
4. Create a single interrupt handler function:
   - Use the interrupt function inputs (e.g., `gpio` and `events`) to determine whether to increment or decrement the counter.
5. In the main loop:
   - Continuously check for button activity and handle it by printing the updated counter value using `\r`.

### Resources

- [Raspberry Pi Pico C/C++ SDK](https://www.raspberrypi.com/documentation/microcontrollers/c_sdk.html)
- [Getting started with Raspberry Pi Pico-series](https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf)
- [Pico-sdk datasheet](https://datasheets.raspberrypi.com/pico/raspberry-pi-pico-c-sdk.pdf)
- [Pico Examples](https://github.com/raspberrypi/pico-examples)

## Building the Project

1. Open terminal.

2. Navigate to this folder:

   ```sh
   cd student-packages/lecture-1/
   ```

3. Create a build directory and navigate into it:

   ```sh
   mkdir build
   cd build
   ```

4. Configure the project with CMake:

   ```sh
   cmake ..
   ```

5. Build the project (call this to rebuild the project):
   ```sh
   cmake --build .
   ```

## Flashing the Firmware

1. Connect the RP2040 board to your computer.
2. Press and hold the BOOTSEL button while plugging the board into USB.
3. Copy the generated `.uf2` file from the `build` directory to the RP2040 USB mass storage device.

### Flashing the Firmware with Picotool

1. Connect the RP2040 board to your computer.
2. Ensure the board is in BOOTSEL mode by pressing and holding the BOOTSEL button while plugging the board into USB.
3. Install `picotool` if you haven't already. Follow the instructions [here](https://github.com/raspberrypi/picotool).
4. Use `picotool` to load the firmware:

   ```sh
   picotool load -f lec1.uf2
   ```

5. Reset the board to start running the new firmware.