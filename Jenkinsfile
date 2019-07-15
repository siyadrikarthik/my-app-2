node{
  try{
      stage('Email-Notification'){
    emailext body: 'Jenkins Build Started', subject: 'Jenkins - jenkinsfile-git-and-maven', to: 'sandsiyatest@gmail.com'
  }
  stage('SCM Checkout'){
    git 'https://github.com/sandeepsiyadri/my-app-2'
  }
  stage('Compile-Package'){
    def mvnHome = tool name: 'MVN3.3', type: 'maven'
    sh "${mvnHome}/bin/mvn packages"
  }
  stage('Slack-Notification'){
    slackSend channel: '#jenkins-learning', color: 'good', iconEmoji: '', message: 'Welcome to Jenkins Slack!', tokenCredentialId: 'slack-key', username: 'jenkins'
  }
  } catch (err){
    emailext body: "Error message: ${err}", subject: 'Jenkins - jenkinsfile-git-and-maven FAILED', to: 'sandsiyatest@gmail.com'
  }
}
