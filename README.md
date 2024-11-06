
# CICD with Docker
A sample Node.js app with continous integration and deployment

## Requirements
- Docker 🐋
- Jenkins

## Setup
- Jenkinsfile placed in root directory, you can setup a multi-branch pipeline with Github.
- Create personal token access in Github with repo and hook scopes.
- You can setup a github server from global settings with generated token for registering hooks

## Steps
See Jenkinsfile and scripts directory. 
- Test 
	-  Source code is tested using `node:10.17.0`
- Package
	-	Docker image is built with commit id , also same image is tagged with latest tag
- Deploy
			- Updates ngnix config by replacing the upstream with latest deployed container.

## Author
- [Zulkafil Tabish](http://github.com/ta6ish)