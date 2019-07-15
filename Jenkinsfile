node{
  stage('SCM Checkout'){
    git 'https://github.com/sandeepsiyadri/my-app-2'
  }
  stage('Compile-Package'){
    def mvnHome = tool name: 'MVN3.3', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
  stage('Email Notificaton'){
    mail bcc: '', body: '''Hi Sand,

    This is to notify that above job build is successful.

    Thanks,
    Jenkins Support Team''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job Notification - jenkinsfile-git-and-maven job ', to: 'sandsiyatest@gmail.com'
  }
  stage('Slack-Notification'){
    slackSend channel: '#jenkins-learning', color: 'good', iconEmoji: '', message: 'Welcome to #jenkins-learning Slack!', teamDomain: 'DevOps', tokenCredentialId: 'slack-jenkins', username: 'jenkins-bot'
  }
}
