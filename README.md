# Bootloader Project

This project is a simple bootloader written in x86 assembly. The bootloader is designed to run on a virtualized environment such as Bochs and demonstrates basic low-level programming concepts like screen manipulation, cursor movement, and printing text.

## Project Structure

- **`boot.asm`**: The main assembly source file for the bootloader. It contains the code to clear the screen, move the cursor, and print a message.
- **`boot.com`**: The compiled binary file for the bootloader.
- **`bochsrc.txt`**: Configuration file for the Bochs emulator. It specifies the memory, ROM images, and boot sequence.
- **`bochsout.txt`**: Log file generated by Bochs during execution.
- **`.gitignore`**: Specifies files and directories to be ignored by Git.
- **`README.md`**: This file, providing an overview of the project.

## Features

- Clears the screen using BIOS interrupts.
- Moves the cursor to a specified position.
- Prints a custom message: `"Oh boy do I sure love assembly!"`.
- Halts the CPU after execution.

## How to Run

1. Assemble the `boot.asm` file into a binary using NASM:

   ```bash
   nasm -f bin boot.asm -o boot.com

   ```

2. Run the bootloader in Bochs:

- Ensure bochsrc.txt is configured correctly to use boot.com as the bootable floppy.
- Start Bochs:

```bash
  bochs -f bochsrc.txt
```

3. Observe the output in the Bochs emulator window.

## Requirements

- NASM: The Netwide Assembler for assembling the bootloader.
- Bochs: An x86 emulator for running the bootloader.

## Notes

- The bootloader is limited to 512 bytes, as required by the BIOS bootloader specification.
- The last two bytes of boot.asm are the boot signature (0xAA55), which is required for the BIOS to recognize the file as a bootable disk.
