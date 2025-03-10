pipeline{
    agent{
        //label 'jenkins-node-aws'
        any
    }
    stages{
        stage('build'){
            steps{
                script{
                    sh 'echo "Build in progress."'
                }
            }
        }
     stage('test'){
            steps{
                script{
                    sh 'echo "Jenkins_repo"'
                }
            }
     }

    }
post {
  success {
    slackSend channel: '#jenkins-project', color: 'warning', message: "Build successed- ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'myproject-z6y6816', tokenCredentialId: 'Slack-notifi'
  }
   failure {
    slackSend channel: '#jenkins-project', color: 'warning', message: "Build failed- ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'myproject-z6y6816', tokenCredentialId: 'Slack-notifi'
  }
}
}


