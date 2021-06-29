pipeline{
    agent {
        label 'master'
    }
    environment{
        docker_hub_account = "ricardomiguel"
        repo_name = "python_notes_app"
        image_tag = "latest"
    }
    stages{
        stages("Build Image"){
            steps{
                //Assemble Image Name
                image_full_name = "${docker_hub_account}/${repo_name}:${image_tag}"
                echo "Image name: ${image_full_name}"

                //Build Image

            }
        }
        stage("Publish Image"){
            steps{
                //docker login
                echo "placeholder"
                //Publish image

            }
        }
    }
}