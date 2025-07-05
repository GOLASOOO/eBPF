# What is eBPF
eBPF is a technology that allows to create custom programs into a Linux kernel at runtime, extending its original functionality.

## Pros of eBPF as a technology:
- **Fast shipping:** Traditionally, providing a Linux kernel with new features took much time due to security concerns and testing even it it was accepted by the community. On the other hand, eBPF provides a verifier so that the program is unable to harm the system.
- **Runtime deployments:** No need to reboot the system or any of its running processes when a new eBPF program is added.
- **No context switching:** eBPF programs runs in the kernel, not in user mode. So whenever an interrupt is arisen and the cpu changes into priviledge mode, there is no need for additional context switching for the eBPF program to be run. This makes for really fast programs as CS is a very expensive operation for a computer.

## eBPF in cloud: better than sidecars
Sidecars have many major disadvantages:
- Restarts needed
- Yaml configurations for charts
- Race conditions in readiness probes
- Added overhead traffic and latency for certains configurations