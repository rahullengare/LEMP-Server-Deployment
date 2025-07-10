# LEMP Server Deployment
## LEMP

- **L → Amazon Linux**: Amazon Linux is a secure, stable, and high-performance Linux distribution provided by AWS, optimized for cloud-based applications and EC2 instances.
- **E → Nginx**: Nginx is a high-performance, open-source web server and reverse proxy known for its speed, scalability, and efficient handling of concurrent connections..
- **M → MySQL**: MySQL is an open-source relational database management system that stores and manages application data using structured tables and SQL queries.
- **P → PHP**: PHP is a popular server-side scripting language used to develop dynamic web pages and applications by embedding code into HTML.

## Step 1: Launch an EC2 Instance

1. Go to AWS Console → EC2 
2. Launch Instance.
    - Name → LEMP
    - Choose AMI → Amazon Linux.
    - Instance type → t2.micro
    - Key pair → pem_server_key
    - security group → launch-wizard-1
      
![Project Screenshot](/Images/LEMP-launch.png)

## Step 2: SSH to connect the EC2 Instance

```bash
ssh -i "pem-server-key.pem" ec2-user@ec2-85-53-26-21.compute-1.amazonaws.com
```
![Project Screenshot](/Images/connect.png)

## Step 3: Install LEMP in **Amazon Linux**

1. Update your system

```bash
sudo yum update
```

2. Install Nginx your LAMP server then Start & enable 

> **nginx** → this is open-source web servers used to deliver web content to users.
> 

```bash
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```
![Project Screenshot](/Images/nginx-start-status.png)

3. Install MYSQL your LAMP server then Start & enable

> **mariadb105-serve**r → this is the MySQL database to install or start
> 

```bash
sudo yum install mariadb105-server -y
sudo systemctl start mariadb
sudo systemctl enable mariadb
```
![Project Screenshot](/Images/mysql-start-status.png)

4. Install PHP your LAMP server then Start & enable

> **php** → this is programming language.
> 

```bash
sudo yum install php -y
sudo systemctl start php-fpm
sudo systemctl enable php-fpm
```
![Project Screenshot](/Images/php-start-status.png)

## Step 4: Terminating Your instance

1. Your use are done then got to AWS console 
2. Click on EC2 → instance 
3. Select instance You want to terminated
4. Click on Instance state 
5. Choose **Terminate (delete) instance**
6. Now click delete

![Project Screenshot](/Images/delete-instance.png)
