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
                    echo "my username $docker_cred_USR"
                    echo "my username $docker_cred_PSW"
                    sh 'docker build -t ghassenkhamassi/nodejs-application:1.0 .'
                    sh "docker login -u $docker_cred_USR -p $docker_cred_PSW"
                    sh 'docker push ghassenkhamassi/nodejs-application:1.0'
                    // withCredentials([usernamePassword(credentialsId: 'docker_cred', passwordVariable: 'PASSWORD', usernameVariable: 'USER')]) {
                    //     sh 'docker build -t ghassenkhamassi/nodejs-application:1.0 .'
                    //     sh "docker login -u ${USER} -p ${PASSWORD}"
                    //     sh 'docker push ghassenkhamassi/nodejs-application:1.0'
                    // }
                }
            }
        }
    }
}