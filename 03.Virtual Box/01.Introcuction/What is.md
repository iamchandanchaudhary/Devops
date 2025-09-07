What is Virtualization
Introduction to Virtualization
In this lecture, we will discuss what virtualization is. Understanding virtualization will help you grasp concepts such as cloud computing, containers, and Docker.

One physical computer can perform the job of multiple computers. This is not about multitasking but about running multiple operating systems simultaneously and in parallel on a single computer.

Before Virtualization
Before virtualization existed, it was not possible to run multiple operating systems on one computer. Software, services, and applications such as Tomcat, Apache HTTP Server, or MySQL databases required dedicated servers to run. At that time, the only option was physical computers, like the one you might be using right now to watch this video.

Data centers housed much larger computers, and the prevailing idea was one service per server. More precisely, one main service equaled one server. This approach ensured isolation; for example, if your database server was running, you would not run a web server or web service on the same machine. Running multiple main services on one server was like "putting all our eggs in one basket," which could lead to catastrophic failures.

Servers were always over-provisioned, meaning if 8 GB of RAM was needed, 12 GB would be allocated. The IT team would over-provision servers to avoid running out of resources. However, server resources were mostly underutilized. This over-provisioning resulted in significant capital and operational expenditures related to physical servers, including procurement, stacking, racking, operating system installation, and maintenance.

For example, if a project had ten services, it required at least ten servers, and for high availability, a minimum of twenty servers or more. This made running IT projects a substantial challenge.

Introduction of Virtualization by VMware
VMware introduced the concept of virtualization by creating tools that allowed one computer to run multiple operating systems. This enabled isolation by running multiple operating systems on a single computer and running all services on top of these operating systems. Thus, services were isolated from each other.

You might wonder if this is still "putting multiple eggs in one basket." However, physical computers can be clustered together to distribute virtual machines, addressing this concern.

Virtualization partitions physical resources into virtual resources. To set up and run an operating system, you need a physical computer. With virtualization, you can create multiple virtual computers within a physical machine. Think of these virtual machines as "baby computers" living inside the physical machine. These virtual machines are isolated from each other because each has its own operating system. This discussion focuses on server virtualization and virtual machines, though other types such as network and storage virtualization also exist.

Architecture of Virtualization
The architecture typically consists of the physical hardware at the base, a software tool called a hypervisor on top of it, and virtual machines created by the hypervisor. Each virtual machine has its own operating system and runs applications or main services. This setup ensures isolation between services.

Terminologies
Host OS: The operating system of the physical machine. For example, the OS on your laptop or desktop.
Guest OS: The operating system running inside a virtual machine. Virtual machines are sometimes called guest machines.
VM: Short for virtual machine.
Snapshot: A way to back up a virtual machine. Although we say "machine," a virtual machine is essentially a set of files that can be backed up easily. Every virtualization technology supports snapshots.
Hypervisor: The software tool that enables virtualization by allowing the creation of virtual machines.
Types of Hypervisors
There are two types of hypervisors:

Type 1 (Bare Metal Hypervisor): Runs directly on the physical computer, similar to an operating system. Examples include VMware ESXi and Xen Hypervisor. This type is used in production environments and dedicates the physical machine solely to virtualization.

Type 2 (Hosted Hypervisor): Runs as software installed on an existing operating system, such as Windows, macOS, or Linux. This type is used for learning and testing purposes. Examples include Oracle VM VirtualBox and VMware Server.

The first diagram represents a Type 1 hypervisor setup: the computer runs the hypervisor directly, which manages virtual machines with their own operating systems and applications. Type 1 hypervisors can be clustered to distribute virtual machines across multiple hypervisors, providing high availability. If one hypervisor fails, others can take over running the virtual machines.

The Type 2 hypervisor runs as software on top of an existing operating system. This setup is suitable for learning and testing, allowing you to create virtual machines on your personal computer.

A note on Microsoft's Hyper-V: although it might appear to be a Type 2 hypervisor, it is actually a Type 1 hypervisor.

In the next lecture, we will explore how to perform virtualization and create virtual machines on a computer. We will also automate this setup. These exercises will help you practice Linux and other upcoming tools in this course.

Key Takeaways
Virtualization allows one physical computer to run multiple isolated operating systems simultaneously.
Before virtualization, each main service required a dedicated physical server, leading to underutilized resources and high costs.
Hypervisors enable virtualization and come in two types: Type 1 (bare metal) for production and Type 2 (hosted) for learning and testing.
Virtual machines can be backed up using snapshots, and clustering hypervisors enhances availability and resource distribution.