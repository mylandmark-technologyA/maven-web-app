node{
  def mavenHome = tool name: 'maven3.8.1'
  stage('CodeClone') {
git credentialsId: 'git-credentials5', url: 'https://github.com/mylandmark-technologyA/maven-web-app'
  }
  stage('mavenBuild') {
    sh "${mavenHome}/bin/mvn clean package"
  }

  stage('CodeQuality') {
    sh "${mavenHome}/bin/mvn sonar:sonar"
  // execute the CodeQuality report with sonar
  }
  stage('emailQualityIssues') {
    //emailext body: '''Thanks
//Landmark Technologies''', recipientProviders: [developers()], subject: 'status of build', to: 'mylandmarktech@gmail.com'
  }

   stage('UploadNexus') {
    //sh "${mavenHome}/bin/mvn deploy"
    //mvn deploy  are uploaded in to nexus
  }
stage('DeployTomcat') {
//deploy adapters: [tomcat9(credentialsId: 'newtomcat', path: '', url: 'http://18.119.106.80:7000/')], contextPath: null, war: 'target/*war'  
}
stage('emailDeployIssues') {
//emailext body: '''thanks
landmarktechnologies''', recipientProviders: [developers()], subject: 'status of build', to: 'mylandmarktech@gmail.com'
}
}
