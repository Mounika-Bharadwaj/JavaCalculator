node{
  stage('SCM checkout'){
    git 'https://github.com/Mounika-Bharadwaj/JavaCalculator'
  }
  stage('Compile-Package'){
    def mvnHome=tool name: 'maven-3', type: 'maven'
    sh ' ${mvnHome}/bin/mvn package'
  }
  stage('sonarqube analysis'){
    def mnvHome= tool name:'maven-3', type:'maven'
    withSonarQubeEnv('sonar-6.7.7'){
    sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
    stage('email notification'){
      mail bcc: '', body: 'Hai , Welcome !', cc: '', from: '', replyTo: '', subject: 'jenkins email notification demo', to: 'aswdevops2699@gmail.com'
  }
  stage('slack notification'){
    slackSend baseUrl: 'https://hooks.slack.com/services/', 
      channel: '#jenkins-pipeline-demo',
      color: 'good',
      message: 'welcome to slack',
      tokenCredentialId: 'slack-demo'
  }
}
  
