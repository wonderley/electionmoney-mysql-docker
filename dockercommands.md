# Using Docker to run the MySQL database

First, install Docker. On Windows or Mac, install Docker Desktop.

Pull the mysql Docker image:
`docker pull mysql`

Run the image to create a container instance. Mount the SQL scripts to the specified directory so that they will be run when the container initializes.
`docker run -d --name electionmoney-mysql -v `pwd`/sql:/docker-entrypoint-initdb.d/ -e MYSQL_ROOT_PASSWORD=my-secret-pw -e MYSQL_DATABASE=electionmoney mysql`

The docker exec command allows you to run commands inside a Docker container. The following command line will give you a bash shell inside your mysql container:

`docker exec -it electionmoney-mysql bash`