pipeline { 

    environment { 

        registry = "itsmeteja9/nodejs-docker" 

        registryCredential = 'dockerjenkinsintegration' 

        dockerImage = '' 

    }
   
    stages { 

        stage('Compile and Build Jar') { 

            steps { 

                bat 'npm install'

            }

        } 

        stage('Building our image') { 

            steps { 

                script { 

                    dockerImage = docker.build registry + ":$BUILD_NUMBER" 

                }
            } 
        }

        stage('Deploy our image') { 

            steps { 

                script { 

                    docker.withRegistry( '', registryCredential ) { 

                        dockerImage.push() 

                 }

                } 

            }

        } 

        stage('Cleaning up') { 

            steps { 

                sh "docker rmi $registry:$BUILD_NUMBER" 

            }

        } 

    }

}
