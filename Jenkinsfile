node {
    pipelineTriggers([
        pollSCM('H/2 * * * *')
    ])
    
    withDockerContainer(image: 'node:16-buster-slim', args: '-p 3000:3000') {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}