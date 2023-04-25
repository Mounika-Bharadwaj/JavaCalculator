node{
  stage('SCM checkout'){
    git 'https://github.com/Mounika-Bharadwaj/JavaCalculator'
  }
  stage('Compile-Package'){
    def mvnHome=tool name: 'maven-3', type: 'maven'
    sh ' ${mvnHome}/bin/mvn package'
  }
    stage('email notification'){
      mail bcc: '', body: 'Hai , Welcome !', cc: '', from: '', replyTo: '', subject: 'jenkins email notification demo', to: 'aswdevops2699@gmail.com'
  }
}
  
