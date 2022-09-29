node {
def mavenHome = tool name: "maven3.8.5"  
echo "Jekins url is : ${env.JENKINS_URL} "
echo "Node name  is : ${env.NODE_LABELS} "
echo "Job name  is : ${env.JOB_NAME} "

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])

stage('CheckOutCode'){
git branch: 'development', credentialsId: 'b90e9bbe-7402-42b8-8424-11471f835d16', url: 'https://github.com/santoshkovvada/maven-web-application.git'
  }
/*
stage('Build'){
sh "${mavenHome}/bin/mvn clean package"

}
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}

stage('UploadArtifactsIntoArtifactoryRepo'){
sh "${mavenHome}/bin/mvn clean deploy"
}
stage('UploadArtifactsIntoArtifactoryRepo'){
sshagent(['f19341b0-47a5-49ea-954a-357ee1d7e3d7']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@52.66.203.249:/opt/apache-tomcat-9.0.65/webapps"   // some block
}
}
*/
 }
