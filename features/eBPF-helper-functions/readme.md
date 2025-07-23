# eBPF helper funcions
## What are BPF helper funcions
They are a set of functions defined in the kernel and used in a eBPF program through the usermode API (UAPI).
Each helper needs a specific set of linux capabilities.

> **Note:** You can learn more about helper functions in [the official eBPF documentation](https://docs.ebpf.io/linux/helper-function/) or [the official man-pages regarding this topic](https://man7.org/linux/man-pages/man7/bpf-helpers.7.html).