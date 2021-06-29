pipeline{
    agent {
        label 'master'
    }
    environment{
        //Docker Hub
        docker_hub_account = "ISTO"
        repo_name = "ISTO"
        image_tag = "latest"
        //docker_hub_login = credentials('ISTO')
    }
    stages{
        stage("Build Image"){
            steps{
                script{
                    //Assemble Image Name
                    image_full_name = "${docker_hub_account}/${repo_name}:${image_tag}"
                    echo "Image name: ${image_full_name}"

                    //Build Image

                }
            }
        }
        stage("Publish Image"){
            steps{
                //docker login
                //bat "docker login -u ${docker_hub_login_USR} -p ${docker_hub_login_PSW}"
                echo "Passou"
                //Publish image

            }
        }
    }
    post{
        always{
            deleteDir()
        }
        success{
            echo "test 1"
            office365ConnectorSend color: '#39c62d', message: 'Build finished successfully', status: 'Success', webhookUrl: 'https://softinsacorp.webhook.office.com/webhookb2/2440de12-bad9-4ed3-8373-f87b862dc0e6@39c83d5e-cede-42d1-962f-c6a853ab7cf5/JenkinsCI/1cf563e41381490e8f616fe72a326a04/a510cf19-d179-4e63-a08e-f5b68fac47ba'
        }
        failure{
            echo "test 2"
            office365ConnectorSend color: '#802311', message: 'Build failed to execute', status: 'Failure', webhookUrl: 'https://softinsacorp.webhook.office.com/webhookb2/2440de12-bad9-4ed3-8373-f87b862dc0e6@39c83d5e-cede-42d1-962f-c6a853ab7cf5/JenkinsCI/1cf563e41381490e8f616fe72a326a04/a510cf19-d179-4e63-a08e-f5b68fac47ba'
        }
    }
}