### Run Jenkins in Docker container

1. Pull latest jenkins Image.

    `docker pull jenkins/jenkins`

    https://github.com/jenkinsci/docker/blob/master/README.md

2. Run jenkins container
    
    `docker run -d --rm --name=my-jenkins -p 8080:8080 -p 50000:50000 -v c:/jenkins/data:/var/jenkins_home jenkins/jenkins:lts-jdk17`

    - -d = detach
    - --rm = remove container once stopped
    - --name == name of the container
    - -p = port mapping
    - -v = local volume mounting

3. Make sure Jenkins container is up and running.

    `docker ps`

4. Retrive the first time password for login

    `docker exec my-jenkins cat /var/jenkins_home/secrets/initialAdminPassword` 

5. Use this password to login

6. Install suggested Plug-ins

7. Create user OR continue with admin.


-----
### Other Commands

- Get into running container

    `docker exec -it my-jenkins /bin/bash`

- List of Jenkins users

    `docker exec my-jenkins cat /etc/passwd`

- List of Projects/Jobs

    `docker exec my-jenkins ls /var/jenkins_home/workspace`

- Tail logs

    `docker logs -f --tail 10 my-jenkins`


