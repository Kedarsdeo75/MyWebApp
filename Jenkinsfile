pipeline {
    agent any
    stages {
        stage(“Build and Testing Stage"){
            steps {
                echo "This is Build and Testing Stage "
            }
        }
        stage(“Deploy to testing environment"){
            steps {
                echo " Deploy to testing environment "
            }
        }
        stage(“Deploy to development environment"){
            steps {
                echo " Deploy to development environment "
            }
        }
        stage(“Deploy to production"){
            steps {
                echo " Deploy to production"
            }
        }
    }
}
                script {
                    img = registry + ":${env.BUILD_ID}"
                    println ("${img}")
                    dockerImage = docker.build("${img}")
                }
            }
        }

        stage('Push To DockerHub') {
            steps {
                script {
                    docker.withRegistry( 'https://registry.hub.docker.com ', registryCredential ) {
                        dockerImage.push()
                    }
                }
            }
        }
                    
        stage('Deploy') {
           steps {
                sh label: '', script: "docker run -d --name ${JOB_NAME} -p 5000:5000 ${img}"
          }
        }

      }
    }
