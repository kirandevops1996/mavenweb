
node{

echo "Job name is:  ${env.JOB_NAME} "
echo "Node name is:  ${env.NODE_NAME}"

def mavenhome = tool name: 'maven3.8.5'

//Get the code from GitHub Repository
stage('checkoutcode'){
git branch: 'development', credentialsId: 'cc5b54f6-54e2-49d6-b2a2-4fb16abf544a', url: 'https://github.com/vali04091988/maven-web-application.git'
}

//Do the build useing maven build tool
stage('Build'){
sh "${mavenhome}/bin/mvn clean package"
}

/*  
//Generating the sonar report
stage('executingthesonarreport'){
sh "${mavenhome}/bin/mvn sonar:sonar"
}

//uploading artifacts into artifact repository
stage('uploadingartifactsintoartifactrepo'){
sh "${mavenhome}/bin/mvn deploy"
}

//Deploying application into tomcat server
stage('Deploying application'){
sshagent(['0cbe3170-1c0a-482a-a067-67e54c561cb7']) {
  sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@43.204.116.174:/opt/apache-tomcat-9.0.62/webapps/"
}

}
*/
}
