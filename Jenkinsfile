node{
  stage('SCM Checkout'){
    git 'https://github.com/sandeepsiyadri/my-app-2'
  }
  stage('Compile-Package'){
    def mvnHome = tool name: 'MVN3.3', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
}
