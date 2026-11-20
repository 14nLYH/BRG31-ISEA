BRG31-ISEA Blog

Lesson 1A /
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

    Learned different basic commands that can be used at the command line interface.
    Kinda like how 'ps -e' is an instance of all process in the vm while 'top' is a
    live version of all the processes running and ls commands to explore different
    files. Editing files with commands was another interesting one with 'gedit' and
    'nano' along with copying, moving and deleting files. Then, we tried to check our
    system info using 'uname -a' and 'lsb_release -a'. An important one was about
    root user and using sudo for admin privileges.

    It was just networking like finding my private ip, pinging local device, talking
    about DNS and how to look up ip for different domains. With abit of software
    installation methods like SaaS, binary and repo.

Lesson 1B /
Linux Commands(SSH, File Permissions, File Search)

  SSH, Firewalls, Services and Compression

    We learned how to install web server like nginx or apache, ssh server using 'sudo apt 
    install' and configure our firewall. We checked out our website with '127.0.0.1 and 
    edited it which i think was pretty cool, tried to SSH a virtual machine from our computer
    and controlling the vm from there. We also learned how to enable our firewall to only
    allow certain ports so bad actors can't easily access of server.

  File Permissions

    We learned Linux file permissions and it is seperated into 3 roles which is user,
    group and others. Using these you can seperate who is allowed to touch what. We created a
    group and allowed them to only read and write and with that we made it so the user can
    read, write and execute while others are unable to access anything with 'sudo chmod 750'.
    The 750 just shows the binary        User Grp Others
                                          rwx rwx rwx
             1 = enabled                  111 101 000
             0 = diabled                   7   5   0
    Then we just adjusted a file with this settings and tested it out with 'su' to switch user.

  File Search

    Last but not least on 1B is file search. It teaches us how to search through files and
    sort them in a certain way to help us look through files faster instead of just searching
    one by one. 'find' and 'grep' i think were my most used commands in this lab activity
    since find was used to search files by size and oldest/youngest while grep was used to
    search for specific phrases, words or sentences. This was overall quite complicated 
    as some of the commands included weird combination of symbols like '%T+ %p\n' and
    's/\s/\n/g'.

Lesson 2A /
TCO and Cloud Web Serber

  TCO Analysis

    Today, i learned to calculate TCO(Total Cost of Ownership) which i don't really have
    much to talk about since it's just a lot of maths. We calculated the total cost of having 
    ownership of 2 things over a period of time and compare after the period which would cost
    less and help a company reduce cost and therefore increase profits. For example, having 
    your own server would be more expensive than cloud as you have to buy a server and hire
    an expert for each of the of the service model and replace parts if it becomes outdated
    or broken and other things whereas with cloud the service provider will settle everything
    and the cost isn't overbearing plus it's way more elastic than building it yourself.

  Cloud Web Server

    This lesson was quite interesting as we learned to create our own web server. I used AWS
    for my web server and honestly it was easier than i imagined it when i was younger or
    maybe it's cause of how much modern society has progressed. I signed up for the free tier
    and made an instance while following the steps given to us. I checked everything like the
    status was running, checks 3/3 passed, i was given a public ip and inbound rules shows
    that my port were open before SSHing into my server. Then we just donwloaded nginx 
    on our ubuntu and checked it out in the browser. After lesson i experimented abit with
    the server like changing the web page adding hyperlinks and whatnot. For now, we are using
    port 80 HTTP but soon we will learn to get a domain name as we are using the public ip 
    of our browser to find it and a TLS certificate so we can use port 443 instead which is 
    HTTPS and is way safer.
    
Lesson 3A /
DNS and SSL

  DNS (Domain Name Server)

    DNS just helps us to keep track of the ip addresses of each domains kinda like our contacts.
    We just learned to claim a domain name for our AWS webserver and later on we are going to 
    get a TLS certificate with certbot. For now, we used duckdns for a free domain name compared 
    to like GoDaddy which is paid and connected it to our web server ip and voila, it is done.
    
  SSL

    This lesson is related to the previous one about web server. After we linked our domain name
    to our web server ip, now we are going to give it a TLS certificate so our server can run on
    HTTPS which helps to protect data using RSA algorithm. This was quite simple as we just
    downloaded certbot and had it give us a cert which lasts 90 days but will automatically renew 
    itself 30 days before expiry. Then, we went on to understand how to secure data in use, data
    at rest and data in motion. For data in use, it mainly uses IAM which is kinda like permissions
    where it controls who can read or change the data. For data at rest it is symmetric encryption
    while data in motion is asymmetric encryption. Data at rest is data that is in storage and the
    current symmetric encryption people use is AES since DES and 3DES is not secure anymore while
    data in motion is well, data that is moving. It uses RSA algorithm to create a key pair that is
    linked, one public and one private. A public key encrypts data while a private key helps to 
    decrypt data that its counterpart encrypted. Each pair can only be used with their linked 
    counterpart so i can't user my private key on someone elses public key encrypted data. I was
    curious about the keys since i didn't understand, like if you the formula for one key pair,
    wouldn't they all be the same and can be reversed so i researched. I found out that they used 
    2 obsurdly large prime numbers, about 300 digits and use them in a formula and user the
    remainders to create the keys which i barely understood it since it's a lot of maths. The point
    is that it will take a modern computer about millions of years to crack one key pair so it is
    nearly impossible to crack.
