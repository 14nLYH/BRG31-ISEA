BRG31-ISEA Blog

Lesson 1A
My First Virtual Machine - Setting up a Linux hypervisor

  What is a virtual machine and how does a hypervisor create one ?

    A virtual machine is a virtual computer that has 
    its own OS(operating system) and apps inside of another 
    physical computer while sharing some of its physical 
    hardware resource like CPU, memory and storage.

    A hypervisor is able to create one by allocating
    slices of the host computer(physical)'s resources
    to every virtual machine that you own. There's 2
    kinds of hypervisor - Type 1 (bare metal) and Type 2.
    Type 1 hypervisor is a hypervisor that runs directly on 
    the host machine without a host OS usually for data centers.
    Type 2 is what we are doing in this lesson where we 
    have our host OS(Windows) and we download a hypervisor
    like an application that doesn't affect our current OS 
    or computer.

  How to setup a hypervisor with an OS.

    Step 1 - Pick a Virtualization tool(Hypervisor) and a Linux OS
    For me it was between VMware or VirtualBox. I did some research and most
    people prefer VMware for better performance but i had trouble signing
    up so i just used VirtualBox instead so i can continue with the lesson. For the
    Linux OS, i followed the lesson plan and used Ubuntu.

    Step 2 - Configuring the VM
    After we downloaded both the hypervisor and the ISO file of our Linux
    OS, we configure the VM to use up how much of our hardware resource
    and booted it up with the ISO file and install Ubuntu on it. Then, configure 
    in the VM itself to allow bridged or NAT internet access so that your VM
    can connect to the internet.

    That's it for the setup. If you want to just run a Linux environment without
    having to setup a VM or download a hypervisor, you can use WSL which allows you
    to do just that without having the trouble of doing all the steps before and
    it starts up faster compared to having to start up an entire machine.


Understanding CLI on Ubuntu

  CLI Basics
