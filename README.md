# jenkins-intermediate

## What is Jenkins
Jenkins is an open-source automation server used to automate parts of the software development process like building, testing, and deploying applications. It helps implement Continuous Integration (CI) and Continuous Delivery (CD) pipelines, ensuring faster and more reliable software delivery.

## Jenkins infrastructure
- Master : controls pieplines & schedule builds.
- Agent : perform the build.
- Pipeline : Github push -> Jenkins get the notif -> Trigger the pipeline -> schedule the build to an agent -> the agent run the build
- Agents : 
  1. Pernament Agent : Standalone (linux/windows) configured to run jobs, just need (java + ssh), build tools needed for the dedicated pipeline.
  2. Cloud Agent : Docker, K8s & AWS.

## Build types
- Freestyle : easy, simple to learn (just a shell script).
- Pipelines : Groovy syx, stages based :
  1. clone: pulling down the code from the git repo
  2. build: builds the code 
  3. test: runs tests against the build
  4. package: pacakged up to be ready for deployment
  5. deploy/delivry: example send docekr image to registry

## Jenkins steup
1. Follow the instructions : https://www.jenkins.io/doc/book/installing/docker/
2. Password : 
3. Configure first Jenkins

## Freestyle : Run a shell script

## Freestyle : Run a python script

## Freestyle : Run shell/in cloud agent
1. Install Docker plugin
2. Create Cloud Agent
3. Configure details
4. To run agent inside a docker in the host
   1. alpine/socat container to forward traffic from Jenkins to Docker Desktop on Host Machine, https://stackoverflow.com/questions/47709208/how-to-find-docker-host-uri-to-be-used-in-jenkins-docker-plugin : docker run -d --restart=always -p 127.0.0.1:2376:2375 --network jenkins -v /var/run/docker.sock:/var/run/docker.sock alpine/socat tcp-listen:2375,fork,reuseaddr unix-connect:/var/run/docker.sock
   2. docker ps (get the name of the container)
   3. docker inspect <container_id> | grep IPAddress -> 172.18.0.3
   4. Configure template
   5. Run build

## Freestyle : Run Python script/in cloud agent 
1. Create new image using the DockerFile.agent
2. Create a local registry
3. Push it to local registry

## Freestyle : Run Python script/in cloud agent auto
1. Fork the repo : https://github.com/devopsjourney1/jenkins-101
2. In jenkins enable trigger Poll SCM H/5 * * * * 
3. Update python script and wait

## Pipeline + DegitalO