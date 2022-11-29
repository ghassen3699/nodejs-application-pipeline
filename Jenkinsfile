pipeline{
    agent any
    stages{
        stage('deploy image'){
            steps{
                script{
                    echo "deploy image"
                    withCredentials([
                        usernamePassword(credentials: 'docker_cred', passwordVariable:PASS, usernameVariable:USER)])
                        {
                            sh 'docker build -t ghassenkhamassi/nodejs-application:1.0 .'
                            sh "docker login -u ${USER} --password-stdin"
                            sh 'docker push ghassenkhamassi/nodejs-application:tagname'
                        }
                }
            }
        }
    }
}