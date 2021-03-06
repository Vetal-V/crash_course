## DevOps Crash Course

1. Run containers using docker-compose
	- To run containers create file with envirovment variables `MYSQL_ROOT_PASSWORD`, `MYSQL_USER` and `MYSQL_PASSWORD`, for example:
		```
		MYSQL_ROOT_PASSWORD=root
		MYSQL_USER=user_wp
		MYSQL_PASSWORD=password_wp
		```
	- Then run docker-compose detached execute the command:
		```
		docker-compose up -d
		```
2. Build image:
	- To builds the images of LAMP stack from a Dockerfile run commands:
		```
		docker build -t lamp:v1 -f Dockerfile.lamp .
		```

	- To builds the images of Wordpress on LAMP stack from a Dockerfile run commands:
		```
		docker build -t wordpress:v1 -f Dockerfile.wordpress .
		```
3. Run container
	- To run the container of LAMP stack execute the command:
		```
		docker run -d -p 80:80 --name=lamp lamp:v1
		```
		- To ensure Apache is running, enter the IP address of your server in the address bar:
			```
			http://pubic-ip-address
			```
		- To confirm that PHP is installed append `/info.php` to the server’s URL:
			```
			http://pubic-ip-address/info.php
			```
	- To run the container of Wordpress on LAMP stack execute the command:
		```
		docker run -d -p 80:80 --name=lamp wordpress:v1
		```

		- To ensure that WordPress wizard ready to install enter the URL:
			```
			http://pubic-ip-address/wordpress
			```
		- You’ll be presented with a WordPress wizard and a list of credentials required to successfully set it up

4. Pull from Docker Hub
	- To pull the image of LAMP stack from Docker Hub run command:
		```
		docker pull vetalvr/crash_course:lamp
		```
		- To run the container of LAMP stack from Docker Hub execute the command:
			```
			docker run -d -p 80:80 --name=lamp vetalvr/crash_course:lamp
			```
	- To pull the image of Wordpress on LAMP stack from Docker Hub run command:
		```
		docker pull vetalvr/crash_course:wordpress
		```
		- To run the container of Wordpress on LAMP stack from Docker Hub execute the command:
			```
			docker run -d -p 80:80 --name=lamp vetalvr/crash_course:wordpress
			```