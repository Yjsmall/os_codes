**调试 MBR 中的加载器**：我们使用实验框架在 bare-metal 上运行了 Hello World，这也是 “最小” 操作系统的雏形——你可以在此基础上实现任何操作系统内核。通过适当的 gdb 指令 (这次是更好用的 Python，取代了历史遗留的 gdb scripts)，我们完成配置的同时指定正确的二进制文件，调试硬件上的代码，与调试普通的程序完全没有区别。

如果希望深入了解编译的全过程，遵循 “一切都是状态机” 的原理，我们可以观察 Makefile (程序)，也可以观察它的执行，而它的执行就是一个个的命令。`make log` 对输出的日志做了一些简化处理，已经足够人类可读，稍加整理就能看到磁盘镜像的编译过程。你也许会感到有些吃惊：世界上所有操作系统的构建过程 (例如 Linux)，都和这个简化版类似，只是多了更多实用的特性：支持分区表、支持压缩/解压缩等。