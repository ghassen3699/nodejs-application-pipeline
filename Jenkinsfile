pipeline{
    agent any
    stages{
        stage('build image'){
            steps{
                script{
                    echo "build image"
                    sh "docker build -t nodejs-app:1.0 ."
                }
            }
        }

        stage('deploy image'){
            steps{
                script{
                    echo "deploy image"
                }
            }
        }
    }
}