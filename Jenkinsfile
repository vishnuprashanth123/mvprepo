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
    sh "scp -o StrictHostKeyChecking=no webapp/Target/webapp.war ec2-user@43.205.94.198:/opt/tomcat/webapps"
}
                
}
}}}

