# Altair 8800 Browser Emulator

The repository retains the original Arduino/desktop Altair 8800 simulator. A static browser front end is provided under `site/` and deployed with GitHub Pages.

## Browser features

- 64 KiB memory model
- Intel 8080-style registers and flags
- front-panel address LEDs and switches
- reset, run, stop, and single-step controls
- hexadecimal program loading at address 0000
- memory inspection and byte editing
- basic console output through port 00
- simple 8080 disassembly view

The browser CPU is currently a practical interactive subset, not a cycle-accurate or instruction-complete replacement for the native `cpucore_i8080.cpp`. The native implementation remains the authoritative reference for complete 8080 behavior.

## Smoke test

Load `3E 41 D3 00 76` and press **RUN**. The program loads A with `0x41`, writes ASCII `A` to output port `00`, and halts.

## Next fidelity phase

1. Port the complete 256-opcode 8080 table and exact flag behavior.
2. Add instruction cycle timing.
3. Map the native I/O devices into browser peripherals.
4. Add Intel HEX/BIN loading and memory export.
5. Add disk-image and CP/M boot support.
6. Evaluate a WebAssembly build of the native core for instruction-level parity.
