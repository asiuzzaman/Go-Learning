 Golang With Database
 ===================
 1.First of all you have to install docker in your local pc because it helps you to install database too faster.
 # For installing docker follow the link below:
 https://docs.docker.com/install/linux/docker-ce/ubuntu/
 
 If docker installation is completed, then you have to running it up and it's time to get a database and connect to in from out GO program.
 At first we have try to get MySQL up and running. For starting a MySQL instance, please follow this command:
 $docker run --name mysqldb -v $HOME/docker/test:/var/lib/mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -d mysql
 Let's break down the command and see what everything means:
 --name mysqldb tells that the container contains the name ```mysqlbd```.  
 ```-v $HOME/docker/test``` tells docker image contain in the docker directory in the test file. 
 ```:``` is the seperator 
 ```/var/lib/mysql``` in the docker file the directory is that.
 ```-p 3306:3306``` define the post mapping.
 ```-e MYSQL_ROOT_PASSWORD=root``` The environment of the docker file (e= environment).
 ```d``` define detouch 
 ```mysql``` the latest version of mysql, you can specify the version also.
 
 Finding out the IP address where the docker run
 $ docker inspect <container name> | grep IPAddr
 
we have MySQL now its time to connect to it from golang.
Let's get MySQL driver for golang.
so we run the following command.
$ go get github.com/go-sql-driver/mysql

 
