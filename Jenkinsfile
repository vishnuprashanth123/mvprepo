pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'pull from git'
                git url: 'https://github.com/vishnuprashanth123/vpnrepo.git',
                branch: 'main',
                credentialsId:'githubcredentials'
                
            }
        }
         stage('Build') {
            steps {
                echo 'build'
                sh 'mvn clean package'
                

    }
}
 stage('deploy') {
            steps {
                echo 'deploy'
                sshagent(['web']) {
    // some block

  sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/devpipeline/target/helloworld-1.1.jar ec2-user@43.205.124.178:/opt/tomcat/webapps"
}
                
            }}                  
                
}
}
