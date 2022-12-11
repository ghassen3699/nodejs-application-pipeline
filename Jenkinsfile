pipeline{
    agent any
    stages{
        stage('deploy image'){
            environment{
                docker_cred = credentials('docker_cred')
            }
            steps{
                script{
                    echo "deploy image"
                    sh 'docker build -t ghassenkhamassi/nodejs-application:1.0 .'
                    sh "docker login -u ghassenkhamassi -p Gha94414015@"
                    sh 'docker push ghassenkhamassi/nodejs-application:1.0'
                    // withCredentials([usernamePassword(credentialsId: 'docker_cred', passwordVariable: 'PASSWORD', usernameVariable: 'USER')]) {
                    //     sh 'docker build -t ghassenkhamassi/nodejs-application:1.0 .'
                    //     sh "docker login -u ${USER} -p ${PASSWORD} --password-stdin"
                    //     sh 'docker push ghassenkhamassi/nodejs-application:1.0'
                    // }
                }
            }
        }
    }
}