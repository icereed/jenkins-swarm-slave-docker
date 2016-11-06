# Jenkins swarm slave

[`icereed/jenkins-swarm-slave`](https://registry.hub.docker.com/u/icereed/jenkins-swarm-slave-docker/)

A [Jenkins swarm](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin) slave.

For a container with ssh enabled see
[`icereed/jenkins-slave`](https://registry.hub.docker.com/u/icereed/jenkins-swarm-slave-docker/)

## Running

To run a Docker container passing [any parameters](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin#SwarmPlugin-AvailableOptions) to the slave

    docker run icereed/jenkins-swarm-slave-docker -master http://jenkins:8080 -username jenkins -password jenkins -executors 1

Linking to the Jenkins master container there is no need to use `--master`

    docker run -d --name jenkins -p 8080:8080 icereed/jenkins-swarm-slave-docker
    docker run -d --link jenkins:jenkins icereed/jenkins-swarm-slave-docker -username jenkins -password jenkins -executors 1


# Building

    docker build -t icereed/jenkins-swarm-slave-docker .
