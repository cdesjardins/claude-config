---
description: "Build the andy-board-config firmware (andy app or bootloader, debug or release)"
argument-hint: "[andy|bootloader] [debug|release|flexspi_nor_debug|flexspi_nor_release|sdram_debug|sdram_release]"
allowed-tools: ["Bash"]
---

# Build andy-board-config Firmware

The project root is `~/sw/berlin/andy-board-config/`.

Parse `$ARGUMENTS` to determine target and build type:
- **target**: `andy` (default) or `bootloader`
- **build_type**: `debug` (default), `release`, `flexspi_nor_debug`, `flexspi_nor_release`, `sdram_debug`, `sdram_release`

Run the build from the appropriate armgcc directory using the shared `build.sh`:

```bash
cd ~/sw/berlin/andy-board-config/<target>/armgcc && ../../build.sh <build_type> 2>&1
```

Report the result:
- **Success**: confirm what was built and the location of the output binary (`.elf` or `.bin` in the `<build_type>/` subdirectory).
- **Failure**: show the relevant error lines so the user can diagnose the problem.

Do not flash the device unless explicitly asked.
