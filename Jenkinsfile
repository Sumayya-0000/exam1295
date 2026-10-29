pipeline{
    agent any
        stages{
            stage('Build'){
                steps{
                    echo 'Building image...'
                    bat "docker build -t mypythonflaskapp ."
                }
            }
            stage('Run'){
                steps{
                    echo 'Running the Docker image ...'
                    bat "docker rm -f mycontainer || exit 0"
                    bat "docker run -d -p 5000:5000 mypythonflaskapp"
                }
            }
        }
        post{
        success{
            echo 'Pipeline completed successfully!'
        }
        failure{
            echo 'Pipeline failed. Check Jenkins Console Output!'
        }
    }
}