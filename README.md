<h1> Deploying a python Web Application Using Docker on AWS EC2 </h1>

## Set up an AWS EC2 instance

1. **Create an IAM user & login to your AWS Console**
   - Access Type - Password
   - Permissions - Admin

2. **Create an EC2 instance**
   - Select an OS image - Ubuntu
   - Create a new key pair & download `.pem` file
   - Instance type - t3.micro

3. **Connecting to the instance using ssh**

   ```ssh -i instance.pem ubunutu@<IP_ADDRESS>```
4. **Configuring Ubuntu on remote VM**
   - Updating the outdated packages and dependencies
     
     ```sudo apt update```
5. **Install Docker**
   ```                                                                                                                                                                    
   sudo apt update 
   sudo apt install docker.io -y
6. **Grant Access to your user to run docker commands**
To grant access to your user to run the docker command, you should add the user to the Docker Linux group.
Docker group is create by default when docker is installed.

    ```
   sudo usermod -aG docker ubuntu
  7. **Start Docker daemon**
     You use the below command to verify if the docker daemon is actually started and Active
    
      ```
      sudo systemctl status docker
8. If you notice that the docker daemon is not running, you can start the daemon using the below command

      ```
      sudo systemctl start docker
9. **Docker is Installed, up and running 🥳**

   Use the same command again, to verify that docker is up and running.

    ```
    docker run hello-world
10. **Clone this repository and move to python-web-app folder**
     ```
     git clone https://github.com/iam-veeramalla/Docker-Zero-to-Hero
     cd  python-web-app

11.
     ```
     docker build .

12.
    ```
    docker run -p 8000:8000 -it successfull-id
NOTE - We will have to edit the inbound rules in the security group of our EC2, in order to allow traffic from our particular port

## Project is deployed on AWS 🎉
