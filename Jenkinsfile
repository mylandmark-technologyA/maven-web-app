node
{
def mavenHome = tool name: 'maven3.8.6'
  stage('CodeClone') 
  {
    git credentialsId: 'git-credential1', url: 'https://github.com/ndimukong2021/web'
  }
stage('mavenBuild') 
{
    sh "${mavenHome}/bin/mvn clean package"
}
/*stage('3. CodeQuality')
{
   // sh "${mavenHome}/bin/mvn sonar:sonar"
} 
stage('emailQualityIssues')
{
   // emailext body: '''thanks
landmark technologies''', recipientProviders: [developers()], subject: 'status of build', to: 'ndimukongndeh@gmail.com'
}
stage('4.UploadNexus') 
{
//sh "${mavenHome}/bin/mvn deploy"
}
stage('5. Approval') 
{
//echo "Approved. Ready for deployment"
}
stage('6. DeployTomcat') 
{
//deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.134.88.232:7000/')], contextPath: null, war: 'target/*war'
}
stage('7. emailNotification')
{
   // emailext body: '''thanks
landmark technologies''', recipientProviders: [developers()], subject: 'status of build', to: 'ndimukongndeh@gmail.com'
}
}
*/
