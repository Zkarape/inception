# inception


42 School Docker Project: Deploying a Personal Server with Docker Compose

📚 Project Overview
inception is a 42 school project aimed at introducing students to system administration and DevOps fundamentals.
The goal is to virtualize a small infrastructure using Docker and Docker Compose, deploying several services inside individual containers.
Each service is built from its own custom Dockerfile, ensuring that students understand containerization from the ground up.

🛠️ Features
Custom Dockerfiles for each service

Docker Compose orchestration

WordPress website served with:

Nginx (reverse proxy + SSL/TLS with self-signed certificates)

MariaDB (MySQL-compatible database server)

PHP-FPM for dynamic processing

Bonus Services (Optional)

Redis for object caching

Adminer or phpMyAdmin for database management

FTP Server (e.g., vsftpd)

Static Website hosting (e.g., with Nginx)

Persistent Data

Volumes are used to keep data between container restarts

Security Measures

Use of non-root users inside containers

SSL encryption

Proper configuration of services

Resource Isolation

Containers are configured with limited privileges

⚙️ How to Run
Prerequisites
Docker

Docker Compose

Make

Installation
Clone the repository:

bash
Copy
Edit
git clone https://github.com/your_username/inception.git
cd inception
Copy .env example:

bash
Copy
Edit
cp .env.example .env
Modify your .env file to fit your domain, passwords, and configurations.

Build and start the containers:

bash
Copy
Edit
make up
Shut down all services:

bash
Copy
Edit
make down
Clean up containers, networks, volumes:

bash
Copy
Edit
make fclean
Rebuild from scratch:

bash
Copy
Edit
make re
🌐 Services Overview

Service	Description	Port
Nginx	Web server with SSL/TLS	443
WordPress	CMS powered by PHP and MySQL	443
MariaDB	Relational database server	3306
Redis	(Bonus) Caching layer	6379
Adminer	(Bonus) Database management tool	8080
FTP Server	(Bonus) File Transfer Protocol	21
🧱 Project Structure
arduino
Copy
Edit
inception/
├── srcs/
│   ├── docker-compose.yml
│   ├── requirements/
│   │   ├── nginx/
│   │   ├── wordpress/
│   │   ├── mariadb/
│   │   └── (bonus services)
│   └── tools/
│       └── (entrypoint scripts, setup files)
├── .env.example
├── Makefile
└── README.md
🔒 Security Notes
Self-signed SSL certificates are generated at container startup.

Database passwords and secrets are injected securely using environment variables.

Volumes ensure that sensitive data persists even if containers are recreated.

✍️ Authors
Zhenya Karapetyan - Zkarape

🏆 Acknowledgements
42 Network

Docker and Docker Compose documentation

WordPress, MariaDB, and Nginx open-source communities

📜 License
This project is for educational purposes under the 42 Network guidelines.****
