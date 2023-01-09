# Jenkins-installation

Since Jenkins runs on Java, you need to install java 11 (previous versions of java wont work)

Installing java

    yum install java-11-openjdk

To change the default java version in the linux server use the command

    update-alternatives --config java
    
To check the java version

    java -version

Update the service with all the latest packages

    yum update (or) yum upgrade


## Installing jenkins

Go to jenkins installation in the official website of jenkins and select linux/ubuntu/centos installation commands of jenkins and execute it one by one

EX - For linux server

    sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
    
To create the jenkins key to access server from the jenkins dashboard

    sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
    
To start/check_status/enable/stop jenkins

    systemctl start jenkins
    
    systemctl status jenkins
    
    systemctl enable jenkins
    
    systemctl stop jenkins
    
    
After starting jenkins, hit the ip of the server with the jenkins port number(8080) in the browser to create/login to the jenkins dashboard

    Ex -   192.168.0.110:8080
    
This will take you to the jenkins getting started page, the jenkins secure key created during the jenkins installation is to be copied and pasted as the administrator password 

The key can be found in the default path

    var/lib/jenkins/secrets/initialAdminPassword
    
You can either install the default plugins suggested by jenkins or select the plugins you want to install in the customise page 

In the next step, create the first admin user credentials and move to the next step which displays the jenkins url. Save and finish the configuration to start using jenkins.


To create a new prject select add item in the jenkins dashboad and name and configure the project to be executed. Save the project.

The project is saved as jobs in jenkins.

To run the project, select the project, then select build now option.


The created jobs in the jenkins console will be reflected in the workspace directory of jenkins in linux in the directory

    var/lib/jenkins/jobs/




Note - To disble firwall 
        
          systemctl status firewalld
          systemctl disable firewalld
    
    
    
    
    
    
    
