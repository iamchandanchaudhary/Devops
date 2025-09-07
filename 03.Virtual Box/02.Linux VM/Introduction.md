# Introduction to Creating Linux Virtual Machines
## Introduction
In this lecture, we will discuss how to create a virtual machine to practice Linux in the upcoming section.

We will be creating two Linux virtual machines in this section: one running CentOS and the other running Ubuntu. These are two very popular flavors of the Linux operating system. We will explore their differences in more detail in the Linux section.

There are two methods for creating virtual machines:

- Manual method: This involves seeing each and every step of creating a VM and installing the operating system. It is wizard-based, where we select multiple options to create the VM.

- Automated method: This allows automatic creation of VMs. You create a text file, issue a command, and the VM will be up and running.

You might wonder why not directly use the automated method since it is fast and simple. The most important rule is: If you want to automate something, make sure you know how to do it manually first.

When you perform a task manually, you understand each step and the entire process. Automation is simply assembling these steps logically using a tool, scripting, or programming language. Never forget this rule in your DevOps career. If you are tasked with automating something, first do it manually.

## Requirements
To create these VMs, you need:

- A 64-bit computer with a high-speed internet connection.
- Your computer can run Windows 10 or 11, macOS with Intel or M1 chip, or even Linux.

Even if you have a Linux desktop, you will still create Linux VMs for practice. This is essential for this course. Later, we will migrate to AWS and work on cloud computing, but initially, Linux VMs are necessary for practice.

Make sure you have completed the prerequisites section where many tools were installed. You need all necessary tools to create VMs.

## Manual VM Creation Tools
For manual VM creation, you will need:

- Oracle VM VirtualBox: This is the hypervisor. Remember this name. If you have any other hypervisor like VMware Desktop, it is recommended not to use it for this course. We will all use Oracle VM VirtualBox to stay on the same pace.

- ISO files: CentOS and Ubuntu ISO files are installation files that you will attach to your VM.

- Login tools: Git Bash or PuTTY will be used to access the VMs.

Note: For macOS with M1 or M2 chips, a different tool will be used instead of VirtualBox.

## Automated VM Creation Tools
For automated VM creation, you still need VirtualBox for Windows and macOS with Intel chips. For macOS with M1 chips, there is a separate lecture covering that.

You will also need Vagrant, a tool that automatically creates VMs by issuing simple commands, which we will explore.

## Labs Overview
There are two labs:

- Manual setup lab: You will use VirtualBox to create a VM by following several steps, download an ISO file, and install the operating system on the VM.

- Automated setup lab: You will create a Vagrantfile with the box name and issue the command vagrant up to create the VM automatically.

Enough talking; let's get into action now. See you in the next lecture.

## Key Takeaways
- Creating Linux virtual machines (VMs) can be done manually or automatically.
- Manual VM creation involves step-by-step installation using Oracle VM VirtualBox and ISO files.
- Automated VM creation uses tools like Vagrant to simplify and speed up the process.
- Understanding manual VM setup is essential before automating tasks in DevOps.