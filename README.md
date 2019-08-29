# Dockerfile with Scala, SBT, Kubernetes, AWS CLI and Docker

This repository contains **Dockerfile** of:
* [Scala](http://www.scala-lang.org)
* [sbt](http://www.scala-sbt.org)
* [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/)
* [AWS CLI](https://aws.amazon.com/cli/)
* [Docker](https://www.docker.com/)
* [Sonar-Scanner](https://docs.sonarqube.org/latest/)
* [Node](https://nodejs.org/en/)

## Base Docker Image ##

* [moia/scala-on-circleci:8u222-2.12.9](https://github.com/CircleCI-Public/circleci-dockerfiles/blob/master/openjdk/images/8u212-jdk-stretch/Dockerfile) [(background)](https://hub.docker.com/r/moia/scala-on-circleci)

## Installation ##

1. Install [Docker](https://www.docker.com)
2. Pull [automated build](https://registry.hub.docker.com/u/moia/scala-on-circleci) from public [Docker Hub Registry](https://registry.hub.docker.com):
```
docker pull moia/scala-node-on-circleci
```
Alternatively, you can build an image from Dockerfile:
```
docker build -t moia/scala-node-on-circleci github.com/moia-dev/scala-node-on-circleci
```


## Usage ##

```
docker run -it --rm moia/scala-node-on-circleci
```

## Development Notes

### Building and publishing docker image

1. Pull latest version from github:

   ```
   git pull origin master
   git fetch --tags
   ```
2. Build Docker image:

   ```
   docker build -t moia/scala-node-on-circleci:8u212-2.12.8-1.14.2-10.16.3 .
   ```
3. Push Docker image:

   ```
   docker login
   docker push moia/scala-node-on-circleci:8u212-2.12.8-1.14.2-10.16.3
   ```

## License ##

This code is open source software licensed under the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").

## Update

1. Edit `Dockerfile` and insert the latest versions of
   * [circleci/openjdk](https://circleci.com/docs/2.0/circleci-images/#openjdk)
   * Scala (https://github.com/scala/scala/releases)
   * Kubectl (https://github.com/kubernetes/kubernetes/releases) 
   * Node (https://github.com/kubernetes/kubernetes/releases) 
2. Make sure the image can be built with `docker build .`
3. Commit and push the changes
4. Create a release on GitHub (https://github.com/moia-dev/scala-on-circleci/releases)
5. Docker Hub will build the image automatically
