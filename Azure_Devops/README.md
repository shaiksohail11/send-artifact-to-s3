install spring pet clinic application
-------------------------------------

1.  sudo apt update -y
2.  sudo apt install openjdk-17-jdk -y
3.  java --version
4.  sudo apt install maven -y
5.  mvn --version
6.  git clone https://github.com/spring-projects/spring-petclinic.git
7.  cd spring-petclinic
8.  mvn clean install package
9.  java -jar target/*.jar

refere here for the spring pet clinic application github repo [referhere](https://github.com/spring-projects/spring-petclinic)


install nopcommerce application
-------------------------------

1. sudo apt update -y
2. curl -fsSL https://get.docker.com -o get-docker.sh
3. sh get-docker.sh
4. git clone https://github.com/nopSolutions/nopCommerce.git
5. cd nopCommerce/
6.  docker image build -t nop:1.0 .
7.  docker image ls
8.  docker container run -d --name kishore -P nop:1.0
9.  docker container ps


refer here for the nopcommerce git hub url [referhere](https://github.com/nopSolutions/nopCommerce)