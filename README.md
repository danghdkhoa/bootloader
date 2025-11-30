# Bootloader Project - Basic Operating System Programming Project

This is a basic bootloader and kernel development project, implemented based on public tutorials.

## 🎥 Tutorial Playlist

I am following this playlist: [https://www.youtube.com/playlist?list=PL2-MHfTy2uA2f46IN1-G8YToRzUMSUi52](https://www.youtube.com/playlist?list=PL2-MHfTy2uA2f46IN1-G8YToRzUMSUi52)

---

## ⚙️ Running and Debugging with GDB & QEMU

To run and debug the source code effectively, you need to use the debugging tool **GDB** and the virtual machine **QEMU**.

### 1. Start GDB and Load Symbols

Open your terminal/command line, navigate to the root directory of the project, and start `gdb`:

```bash
gdb
```

In the gdb environment, enter the following commands sequentially:
### 2. Load the kernel symbols at address 0x100000

```bash
add-symbol-file ./build/completeKernel.o 0x100000
```
# 3. If prompted for confirmation, enter 'y' (yes)
```bash
y 
```

# 4. Set a breakpoint at the kernel_main function

```bash
break kernel_main
```

# 5. Start qemu and Connect the Debugger
```bash
target remote | qemu-system-x86_64 -hda ./bin/os.bin -gdb stdio -S
```