pipeline{
    agent any
    stages{
        stage('deploy image'){
            steps{
                script{
                    echo "deploy image"
                    
                    withCredentials([usernamePassword(credentialsId: 'docker_cred', passwordVariable: 'PASSWORD', usernameVariable: 'USER')]) {
                        sh 'docker build -t ghassenkhamassi/nodejs-application:1.0 .'
                        sh "docker login -u ${USER} -p ${PASSWORD}"
                        sh 'docker push ghassenkhamassi/nodejs-application:1.0'
                    }
                }
            }
        }
    }
}