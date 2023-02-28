pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                git credentialsId: 'githubcredentials', url: 'https://github.com/vishnuprashanth123/vpnrepo.git'
            }
        }
         stage('Build') {
            steps {
                sh "mvn clean package"
    }
}
 stage('deploy') {
            steps {
                sshagent(['tomcat-new']) {
                     sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/devpipeline/target/helloworld-1.1.jar ec2-user@43.205.124.178:/opt/tomcat/webapps"
                }
  }
}
    }}

