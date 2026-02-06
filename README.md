# Network-Monitoring-System
System to continuously observe network and its data flows

# This is a project to get hands-on learning experience with Linux and Networking

**Installing a Hypervisor and Virtual Machine:**

Hypervisor - A Hypervisor is the device or software that runs the virtual machine. It acts as the interface and liason between the "guest" virtual machine and the host system. Hypervisors manages system resources and allocates them to multiple operating systems running on the same physical machine.

Virtual Machine - A software-based computer that runs within a physical computer. (i.e. Running Windows 11 on a Linux Machine). VM's are isolated with their own CPU, memory, storage, etc.

Hypervisor/Virtual Machine use cases:
  - Automation/Scripting
  - Home Server
  - Security Lab
  - Containerization

The Hypervisor I will be using is Kernel-based Virtual Machine (KVM) with QEMU Virtual Machine emulator. KVM has been built into Linux since kernel 2.6.20

At least 50 GB of free storage and 8 GB of RAM is recommended, although more is better.

**Host machine specifications:**

Hostname: pop-os

Architecture: x86-64

1. Ensure virtualization is enabled on the host machine.

   ~ First, verify the host machine's CPU vendor (i.e. Intel or AMD) and determine if virtualization is           enabled on the host machine's CPU. This information can be determined using the following command(s):

     - root@pop-os: egrep -c '(vmx|svm)' /proc/cpuinfo

       *this command searches the /proc/ directory and cpuinfo file to return information about your                 machine's CPU. The -c flag counts the number of times the given expression is detected. If the               returned value is greater than 0 then that means virtualization is enabled on the host machine. If           the returned value is 0 or a blank, then virtualization must be enabled via the system BIOS/UEFI.

       *vmx represents an Intel processor
       
       *svm represents an AMD processor
     
     - root@pop-os: lscpu | grep Virtualization

       *the lscpu command fetches CPU specifications such as Architecture, number of CPU(s), Vendor ID and           Model name, among other information. The grep command is used to search for specific words, phrases          or patterns within text files. Here, the grep command is used in conjunction with lscpu in order to          search for the word "Virtualization".

       *VT-x represents an Intel processor
       
       *AMD-V represents an AMD processor
