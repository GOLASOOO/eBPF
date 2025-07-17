# 🖥️ Environment Overview
This section details the development and runtime environment used for this thesis.

## Host machine
The host system is a MacBook Air with an Apple M3 chip running macOS. 
All development work—including writing code and documentation (Markdown files)—is performed on this machine. 
The host also manages the shared development folder for seamless editing.

## Guest Environment (Execution VM)
The eBPF programs are executed in a Fedora 42 virtual machine running inside VirtualBox. 
This setup provides a Linux environment with kernel support for eBPF features.
Key features of the VM setup include:
- **Shared Folder:** Provides direct access to the project directory from the host.
- **Bidirectional Clipboard:** Enables copying between host and guest for better productivity.
- **Guest Additions Installed:** To enable folder sharing and better integration.
While this VM-based setup works well, I’m considering switching to a lighter containerized environment to reduce resource consumption on the MacBook, which tends to overheat under sustained load (🔥🔥🔥).

## Fedora Setup Commands
To prepare the Fedora VM for eBPF development, the following commands are executed:
```
# Install essential build tools and kernel headers
sudo dnf install -y gcc kernel-devel kernel-headers dkms make bzip2 perl

# Mount and run VirtualBox Guest Additions (only if not already installed)
./run/media/gonzalo/VBox_GAs_7.1.10/VBoxLinuxAdditions.run

# Add the user to the vboxsf group for shared folder access
sudo usermod -aG vboxsf gonzalo

# Install BCC (BPF Compiler Collection) and Python bindings
sudo dnf install -y bcc bcc-tools python3-bcc kernel-devel-$(uname -r)
```