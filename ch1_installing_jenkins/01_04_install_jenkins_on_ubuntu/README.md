# 01_04 Install Jenkins on Ubuntu

Use these instructions to install Jenkins on a system running a Ubuntu operating system.

## **Prerequisites**

Before installing Jenkins, make sure that the system has the following in place:

* A recent version of the Ubuntu operating system (for example, Ubuntu 24.04 LTS)
* At least **256 MB of RAM**
* At least **1 GB of drive space**

You should be able to access the system via Command Line Interface (CLI), most likely over Secure Shell (SSH), and via a browser on port 8080\.

You should have root permission on the target system, specifically so you can run commands using `sudo`.

## **Install Java 21 JDK**

Systems operating Jenkins must have a Java runtime environment installed.

The recommended version of Java for use with Jenkins is Java 21\.  The Java Development Kit (JDK) version includes the Java runtime environment and additional development tools.

1. Open a terminal on the Ubuntu system.
1. Run the following commands to update the package management system and Install openjdk-21-jdk:

   ```bash
   sudo apt-get update
   sudo apt-get upgrade \-y
   sudo apt-get install \-y openjdk-21-jdk
   ```

1. Confirm that the installation completes successfully.

## **Install Jenkins**

Continue in the terminal with the following steps.

1. Install `wget`; this application will be used to download additional resources:
   1. `sudo apt-get install -y wget`
1. Run the following commands to:
   1. download the official signing key for Jenkins packages
   2. update the package manager to include the official sources for Jenkins installation files
   3. update the package manager to refer to the new key and installation sources

    ```bash
   sudo wget \-O /usr/share/keyrings/jenkins-keyring.asc \\

     <https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key>

   echo "deb \[signed-by=/usr/share/keyrings/jenkins-keyring.asc\]" \\

     <https://pkg.jenkins.io/debian-stable> binary/ | sudo tee \\

     /etc/apt/sources.list.d/jenkins.list \> /dev/null

   sudo apt-get update
    ```

1. Run the following command to install Jenkins:
   1. `sudo apt-get install -y jenkins`
1. Confirm that the command completes successfully.
1. Run the following command to retrieve the initial administrator password:
   1. `sudo cat /var/lib/jenkins/secrets/initialAdminPassword`
1. Copy the password for use during the next installation steps
1. Complete the installation by opening a browser and connecting to the system’s network address using port 8080\.
   1. If you are installing Jenkins on a local system, use: [http://localhost:8080](http://localhost:8080)
   2. If you are installing Jenkins on a remote system, specify the system’s network name, for example: [http://system-name.example.com:8080](http://system-name.example.com:8080)

<!-- FooterStart -->
---
[← 01_03 Install Jenkins on macOS](../01_03_install_jenkins_on_macos/README.md) | [01_05 Install Jenkins using Docker →](../01_05_install_jenkins_using_docker/README.md)
<!-- FooterEnd -->
