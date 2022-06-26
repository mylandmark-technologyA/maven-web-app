//Jenkins pipeline script
//Groovy script 

node{
  def mavenHome = tool name: 'maven3.8.1'
  stage('CodeClone') {
    git credentialsId: 'git-credentials', url: 'https://github.com/mylandmarktechs/web'
  }
  stage('mavenBuild') {
    sh "${mavenHome}/bin/mvn clean package"
  }

  stage('CodeQuality') {
    sh "${mavenHome}/bin/mvn sonar:sonar"
  // execute the CodeQuality report with sonar
  }
   stage('UploadNexus') {
   // sh "${mavenHome}/bin/mvn deploy"
    //mvn deploy  are uploaded in to nexus
  }
  stage('deployDocker') {

    sh "docker build -t mylandmarktech/maven-web-app:latest ."
    sh "docker push mylandmarktech/maven-web-app:latest"
    sh "docker rmi -f mylandmarktech/maven-web-app:latest"
    sh "docker rm -f myapp"
    sh "docker run --name myapp -d -p 8888:8080 mylandmarktech/maven-web-app:latest"
    
    }
  stage('emailAlerts') {
    emailext body: '''Thanks
Landmark Technologies''', recipientProviders: [developers()], subject: 'status of build', to: 'mylandmarktech@gmail.com'
  }
}
