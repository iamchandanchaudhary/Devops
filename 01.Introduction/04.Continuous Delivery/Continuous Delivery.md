# What is Continuous Delivery?
## Introduction to Continuous Delivery
Continuous delivery is an automated process of delivering code changes to servers quickly and efficiently at an enormous pace.

My name is Imran, and I will be glad to explain the continuous delivery process.

Continuous delivery is the extension of continuous integration. If you have not seen my previous video on continuous integration, I recommend you watch it before you continue.

We have seen that continuous integration is the automation of our code build and test. When developers commit any code, it will be automatically built and tested. If everything is good, the artifact generated from this process will be stored in software repositories.

The goal of continuous integration is to detect defects at a very early stage so they do not multiply.

The operations team will get regular requests to deploy the artifacts generated from the continuous integration process on servers for further testing.

The operations team, with all the information they have, deploys the artifacts to the servers. At times, the deployment also fails, which leads to higher lead time.

Development and operations teams need to work together to fix such deployment failures, and this happens on and off.

We have to understand that in agile development, there will be regular code changes which need to be deployed on servers for further testing.

Deployment is not just about shipping the software to the servers; it is more than that.

A deployment could also mean server provisioning, installing dependencies on servers, configuration changes, network or firewall rules changes, and then deploying the artifact to the server. There could be many more things involved.

The operations team will be flooded with such requests as the continuous integration process generates artifacts faster and regularly.

After the manual deployment, information will be sent to the QA team for testing. After conducting testing, the QA team will send information back.

There is too much human intervention and manual approval in this process.

As this terminator says, automate it and save your time and also reduce failures.

Any and every step in deployment should be automated.

There are a lot of automation tools available in the market, such as Ansible, Puppet, and Chef for system automation; Terraform for cloud infrastructure automation; Jenkins and Octopus Deploy for CI/CD automation.

There are many others to choose from based on your needs.

Software testing also has to be automated. Any test process like functional, load, performance, database, network, security, and any other test cases.

The operations team will write automation code for deployment, testers will write automation code for software testing, and synchronize it with developers' source code.

Now we have a process integrated with deployment automation, which triggers software testing. All three teams and processes are integrated together.

This is the continuous delivery process.

Automate every step and then stitch everything together. That gives you continuous delivery automation.

## Key Takeaways
- Continuous delivery automates the process of delivering code changes to servers quickly and efficiently.
- It extends continuous integration by automating deployment, server provisioning, configuration, and testing.
- Automation reduces manual intervention, decreases deployment failures, and shortens lead times.
- Various tools like Ansible, Puppet, Chef, Terraform, Jenkins, and Octopus Deploy facilitate automation in deployment and testing.