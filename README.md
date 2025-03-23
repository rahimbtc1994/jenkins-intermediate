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

## 