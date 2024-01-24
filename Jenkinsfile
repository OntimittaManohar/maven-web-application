node ('nodes')
{
def mavenHome = tool name: "maven3.9.6"
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '4', daysToKeepStr: '', numToKeepStr: '4')), pipelineTriggers([pollSCM('* * * * *')])])
stage ('CheckoutCode')
{
git branch: 'development', credentialsId: 'bd9efa78-0b96-474e-b8bc-9a5c5e6de227', url: 'https://github.com/OntimittaManohar/maven-web-application.git'
}

stage ('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage ('ExecuteSonarQubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage ('UploadArtifactIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage ('DeployAppIntoTomcatServer')
{
sshagent(['e774e87e-ece1-41f8-9f7a-d1584c873513']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.109.54.162:/opt/apache-tomcat-9.0.83/webapps"
}
}

stage ('SendEmailNotification')
{
emailext body: '''Build Over...!

Regards,
Manohar,
xxxxxxxxxxx''', subject: 'Build Over', to: 'ontimittam@gmail.com'
}
*/
}
