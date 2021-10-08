# Spinn up a Oracle database inside a Docker container. 

Good for learning and demo.

## Prerequisites

1. Docker installed
2. Docker account

## How

1. Log in to Docker at hub.docker.com
2. Search for Oracle database and click on 'Oracle Database Enterprise Edition'.
3. Click on Proceed to Checkout and accept terms and conditions.
4. Pull the image using this command:  `docker pull store/oracle/database-enterprise:12.2.0.1-slim`
5. Start a container from the image using this command: `docker run -dp 1521:1521 --name <name of container> store/oracle/database-enterprise:12.2.0.1-slim`

6. För att ansluta till databasen: 
```
Hostname: localhost
Port: 1521
SID: ORCLCDB
Role: SYSDBA
Username: SYS
Password: Oradoc_db1
``` 

