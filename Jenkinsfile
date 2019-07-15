node{
  stage('SCM Checkout'){
    git 'https://github.com/sandeepsiyadri/my-app-2'
  }
  stage('Compile-Package'){
    def mvnHome = tool name: 'MVN3.3', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
  stage(){
    mail bcc: '', body: '''Hi Team,

This is to notify that the job built is successful!

Thanks,
Jenkins Support Team''', cc: '', from: 'sandsiyatest@gmail.com', replyTo: '', subject: 'Jenkins Job Notification - jenkinsfile-git-and-maven', to: 'sandsiyatest@gmail.com'
  }
  stage('Slack-Notification'){
    slackSend channel: '#jenkins-learning', color: 'good', iconEmoji: '', message: 'Welcome to Jenkins Slack!', tokenCredentialId: 'slack-key', username: 'jenkins'
  }
}
