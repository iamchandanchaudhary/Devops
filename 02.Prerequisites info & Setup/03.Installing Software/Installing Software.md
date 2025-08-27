# Installing Softwares
## Introduction
In this lecture, we will see how to install the necessary software and tools on a computer for this course. The installation will be performed through the command line, rather than the traditional method of downloading and installing each software manually.

## Choosing the Installation Method
Windows users will use Chocolatey, while macOS users will use Brew. First, open the following URL in your browser:

- github.com/hkhcoder/vprofile-project

This is the repository for the project source code. In this repository, there are multiple branches. Click on the dropdown and find the branch called `prereqs`. Select that branch to access the prerequisite documents. There are four documents in different formats. Download the format you prefer, such as PDF, or view the MD file directly. You can also download the document from the lecture resources.

## Preparing Your Terminal
For Windows users, open PowerShell as Administrator. For macOS users, open Terminal. Execute the commands as listed in the document. The commands for Windows users are listed first, followed by those for macOS users. If you are using macOS, open Terminal and execute the specified command. Copy the command from the document and run it. When you execute these commands, you should see `-k` printed in your terminal. This indicates that the setup is correct, and you can proceed to install the required software.

## Verifying Existing Installations
Before starting the installation, verify your current setup. Windows users should search for PowerShell and run it as Administrator. macOS users should open Terminal. To check the list of installed software, Windows users should run the following command:

``` none Code Sample
choco list
```

macOS users should run:

``` none Code Sample
brew list 
```
You should see the list of installed software through Chocolatey or Brew. Next, check if Maven or Java is already installed by running the following commands:

``` none Code Sample
mvn -version
java -version
```

If you receive an error, you can proceed to install the software. If you see versions listed for Maven or Java, you must uninstall them first. Windows users can uninstall a package using:

``` none Code Sample
choco uninstall <package-name>
```

Search for the package name in the list, such as Maven or Java. The Java package name might differ, for example, `JDK 17` or `Corretto JD 11`. Ensure you use the correct package name from the list. For example, if the package name is `vscode`, use that name in your uninstall command. macOS users should use:

``` none Code Sample
brew uninstall <package-name>
```

With `choco list` or `brew list`, you can easily find the package names to uninstall. Once you have uninstalled any existing versions, you can proceed to install the required tools.

## Installing Required Tools
Refer to the document and begin installing each tool one by one. Use your respective terminal: PowerShell for Windows or Terminal for macOS. Copy the command for each tool, ensuring you use the version specified in the document.

``` none Code Sample
choco install virtualbox
```

For macOS, use the corresponding brew command. Paste the command into your terminal and press Enter. The installation may take some time and might prompt you to confirm with Yes or No. Respond with Yes to proceed.

## Installing Additional Tools
Continue with the next commands as each installation completes. For example, after installing VirtualBox, proceed to install Vagrant.

``` none Code Sample
choco install vagrant
```

Continue installing the following tools in order:

- Git
- Corretto 17 (Java 17)
- Maven
- AWS CLI
- IntelliJ or VSCode (or both)
- Sublime Text editor

Use the commands as specified in the document, and ensure you use the correct versions.

``` none Code Sample
choco install git
choco install corretto17
choco install maven
choco install awscli
choco install intellijidea
choco install vscode
choco install sublime3
```

For macOS, use the equivalent brew commands for each tool.

## Verifying Installation
After completing the installations, you should have the following tools installed:

- Oracle VM VirtualBox
- Git Bash
- Vagrant
- Chocolatey or Brew (depending on your operating system)
- JDK 8
- Maven
- IntelliJ
- Sublime Text editor

Once these tools are ready, you can proceed to the next step, which is signing up for a few accounts.

## sKey Takeaways
- Software installation for the course is performed via command line using Chocolatey for Windows and Brew for macOS.
- Users should verify and uninstall any existing versions of Maven or Java before proceeding with installations.
- The installation process involves executing specific commands for each required tool, following the versions listed in the provided document.
- Both Windows and macOS users must use their respective terminals and commands to install all necessary development tools before moving on to the next steps.