pipeline{
    agent any
    stages{
        stage('deploy image'){
            steps{
                script{
                    echo "deploy image"
                    withCredentials([usernamePassword(credentialsId: 'docker_cred', passwordVariable: 'PASS', usernameVariable:'USER')]){
                        
                        
                        
                    }
                    withCredentials([(credentialsId:'docker_cred',variable:'dockerhubpwd')]){
                        sh 'docker build -t ghassenkhamassi/nodejs-application:1.0 .'
                        sh "docker login -u ghassenKhamassi -p ${dockerhubpwd}"
                        sh 'docker push ghassenkhamassi/nodejs-application:1.0'
                    }
                }
            }
        }
    }
}