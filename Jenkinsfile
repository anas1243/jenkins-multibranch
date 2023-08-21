pipeline {
    agent any
    stages{
        stage('build'){
            steps {
                echo "This is the dev branch after adding github webhook"
                withCredentials([sshUserPrivateKey(credentialsId: 'ssh-key', keyFileVariable: 'webserver_ssh_key', usernameVariable: 'ssh_username'), usernamePassword(credentialsId: 'docker-cred', passwordVariable: 'docker_password', usernameVariable: 'docker_username')]) {
                    sh '''
                    echo $docker_username > test-with-credentials
                    cat test-with-credentials
                    echo "inside the withCredentials plugin"
                    '''
                }
            }
        }
    }
}