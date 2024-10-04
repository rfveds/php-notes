# MySQL Study Plan for Interview Preparation

## Introduction to MySQL

- What is MySQL?
    - MySQL is an open-source relational database management system (RDBMS).
    - It uses SQL (Structured Query Language) for managing and manipulating data.
    - MySQL is widely used for web applications and is known for its reliability, performance, and ease of use.

- MySQL architecture
    - MySQL follows a client-server architecture.
    - The MySQL server is responsible for storing, processing, and managing data.
    - Clients connect to the MySQL server to interact with the database using SQL queries.
    - MySQL supports multiple storage engines, such as InnoDB and MyISAM, each with different features and performance
      characteristics.

- MySQL installation and setup with docker

## Installing MySQL with Docker
1. 
2. Install Docker:
	   - Visit the official Docker website (https://www.docker.com) and download the appropriate version of Docker for your operating system.
	   - Follow the installation instructions provided by Docker.

	2. Create a Docker Compose file:
	   - Create a new directory for your MySQL Docker setup.
	   - Inside the directory, create a file named `docker-compose.yml` with the following contents:

	     ```yaml
	     version: '3'
	     services:
	       db:
		 image: mysql:latest
		 restart: always
		 environment:
		   MYSQL_ROOT_PASSWORD: your_root_password
		   MYSQL_DATABASE: your_database_name
		   MYSQL_USER: your_username
		   MYSQL_PASSWORD: your_password
		 volumes:
		   - ./mysql-data:/var/lib/mysql
		 ports:
		   - "3306:3306"
	     ```

	     Replace `your_root_password`, `your_database_name`, `your_username`, and `your_password` with your desired values.

	3. Start the MySQL container:
	   - Open a terminal or command prompt.
	   - Navigate to the directory where you created the `docker-compose.yml` file.
	   - Run the following command to start the MySQL container:

	     ```
	     docker-compose up -d
	     ```

	     This command will download the MySQL Docker image (if not already present) and start a new container based on the configuration specified in the `docker-compose.yml` file.

	4. Connect to the MySQL server:
	   - Once the container is running, you can connect to the MySQL server using any MySQL client.
	   - For example, you can use the MySQL command-line client by running the following command:

	     ```
	     docker-compose exec db mysql -u your_username -p
	     ```

	     Replace `your_username` with the username you specified in the `docker-compose.yml` file.
	   - Enter the password you specified in the `docker-compose.yml` file when prompted.

	5. Stop and remove the MySQL container:
	   - To stop the MySQL container, run the following command in the same directory:

	     ```
	     docker-compose down
	     ```
	#### Restart explanation
	   - This command will stop and remove the MySQL container, but the data stored in the `mysql-data` volume will persist.
	   
	   In the `docker-compose.yml` file, the `restart: always` option is used to specify the restart policy for the MySQL container.

      The `restart: always` policy means that the container will always be restarted by Docker, regardless of the exit status.
      Here's what it implies:
      
      1. If the container stops due to any reason (e.g., an error occurs, or the container is manually stopped), Docker will
         automatically restart the container.
      
         2. When the Docker daemon restarts (e.g., when the host machine is rebooted), Docker will automatically start the
            container.
      
         3. The container will continue to restart indefinitely unless it is explicitly stopped or removed.
      
      The `restart: always` policy ensures that the MySQL container is always running and available, even if it encounters
      issues or the host machine is restarted.
      
      There are other restart policies available as well, such as:
      
      - `restart: on-failure`: Restarts the container only if it exits due to an error (non-zero exit status).
        - `restart: unless-stopped`: Restarts the container unless it is explicitly stopped or Docker itself is stopped or
          restarted.
        - `restart: no` (default): Does not automatically restart the container under any circumstances.
      
      You can choose the appropriate restart policy based on your specific requirements and the desired behavior of your MySQL
      container.


