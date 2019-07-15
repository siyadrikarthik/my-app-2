node{
  stage('SCM Checkout'){
    git 'https://github.com/sandeepsiyadri/my-app-2'
  }
  stage('Compile-Package'){
    def mvnHome = tool name: 'MVN3.3', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
  stage('Email-Notification'){
    emailext body: '''Hi Team,

This is to notify you that the above build is successful!

Thanks,
Jenkins Support Team''', subject: 'Jenkins - jenkinsfile-git-and-maven - Successful', to: 'sandsiyatest@gmail.com'
  }
  stage('Slack-Notification'){
    slackSend channel: '#jenkins-learning', color: 'good', iconEmoji: '', message: 'Welcome to Jenkins Slack!', tokenCredentialId: 'slack-key', username: 'jenkins'
  }
}
