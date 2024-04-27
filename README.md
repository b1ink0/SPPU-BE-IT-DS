# SPPU-BE-IT-DS
#### Important Requirements & Prerequisites
- java 8
```bash
# install java 8 on Ubuntu
sudo apt update 
sudo apt install openjdk-8-jdk -y
# to check if you have multiple version of java and setting default to java 8
sudo update-alternatives --config java
```
![ALT](./assets/java8.png)
```bash
# now other versions of java needs to be deleted 
# if not deleted Assignment2 will cause an error
# fist list the installed java versions using this command
dpkg --list | grep -i jdk
# now use this command to remove all the components of other version
sudo apt purge openjdk-11-jdk
sudo apt purge openjdk-11-jdk-headless
sudo apt purge openjdk-11-jre
sudo apt purge openjdk-11-jre-headless
# now check again if only java 8 present
dpkg --list | grep -i jdk
```
![ALT](./assets/remove_java_1.png)
![ALT](./assets/remove_java2.png)

- Downlaod java 8 for windows from [Link1](https://builds.openlogic.com/downloadJDK/openlogic-openjdk/8u412-b08/openlogic-openjdk-8u412-b08-windows-x64.msi) or [Link2](https://www.openlogic.com/openjdk-downloads?field_java_parent_version_target_id=416&field_operating_system_target_id=436&field_architecture_target_id=391&field_java_package_target_id=396 
)
<hr>

#### Assignment 1
1. Terminal 1
    ```bash
    # compile all java files
    javac *.java
    # compile implementation file
    rmic ServerImplementation
    # start rmiregistry
    rmiregistry

    ```
2. Terminal 2
    ```bash
    # start the server
    java Server
    ```
3. Terminal 3
    ```bash
    # connect the client
    # for addtion, substraction, division, multiplication
    java Client 10 20
    # for square, square root
    java Client 25
    # for string equal
    java Client abc abc
    # for palindrome
    java Client aba
    ```
<hr>

#### Assignment 2
1. Terminal 1
    ```bash
    # complile all the files
    javac *.java
    # start orbd 
    orbd -ORBInitialPort 1056
    ```
2. Terminal 2
    ```bash
    # start the server
    java ServiceServer -ORBInitialPort 1056
    ```
3. Terminal 3
    ```bash
    # connect the client
    java ServiceClient -ORBInitialPort 1056 -ORBInitialHost localhost
    ```