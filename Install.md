## **Ubuntu**

**Install JDK**

    sudo apt update && sudo apt upgrade
    
    # Verify if Open JDK 17 is available
    apt-cache search openjdk | grep openjdk-17
    sudo apt install openjdk-17-jdk
    
    # Verify if Java is installed
    java --version
    
    # Find the installed JDK path
    update-java-alternatives -l
    
    java-1.17.0-openjdk-amd64 1711 
    /usr/lib/jvm/java-1.17.0-openjdk-amd64
    
    nano /etc/profile
    export JAVA_HOME=/usr/lib/jvm/java-1.17.0-openjdk-amd64
    export PATH=$JAVA_HOME/bin:$PATH
    
    # Verify if the path is set
    echo $JAVA_HOME
    /usr/lib/jvm/java-1.17.0-openjdk-amd64

**Install Maven**

    wget https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.tar.gz
    
    sudo tar xf apache-maven-*.tar.gz -C /opt
    sudo ln -s /opt/apache-maven-3.9.4 /opt/maven
    sudo nano /etc/profile.d/maven.sh
    export M2_HOME=/opt/maven
    export MAVEN_HOME=/opt/maven
    export PATH=${M2_HOME}/bin:${PATH}
    
    sudo chmod +x /etc/profile.d/maven.sh
    source /etc/profile.d/maven.sh
    
    # Find maven version
    mvn -version
    
    Apache Maven 3.9.4 (21122926829f1ead511c958d89bd2f672198ae9f)
    Maven home: /opt/maven
    Java version: 17.0.7, vendor: Private Build, runtime: /usr/lib/jvm/java-17-openjdk-amd64
    Default locale: en, platform encoding: UTF-8
    OS name: "linux", version: "5.15.0-1041-azure", arch: "amd64", family: "unix"

## **Windows**

    **Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))**
