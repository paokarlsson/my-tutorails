# How to setup a Java "Hello World" project to run inside a docker container

## This is all code required


Main.java
```java 
class Main {
	public static void main(String[] args) {
		System.out.println("Hello World");
	}
}
```
Dockerfile
```
FROM openjdk:16-alpine3.13
COPY Main.java Main.java
CMD ["java","Main.java"]
```


## How

1. Download and install Docker
2. Run the following command to make sure the installation succeded `docker --version`
3. Create a folder and create the files as specified above inside it. `Main.java` and `Dockerfile`.
4. Create a image using the Dockerfile by executing the following command: `docker build --tag javaimage .`
5. Create a container and run it using image with this command: `docker run --name javacontainer javaimage`   
6. Hello World should be printed in the terminal.