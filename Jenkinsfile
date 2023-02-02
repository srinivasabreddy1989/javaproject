pipeline {
    agent any

    stages {
        
        stage('Git package') {
            when {
                branch 'main'
            }
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Apache deploy') {
            when {
                branch 'develop'
            }
            steps {
               sshagent(['Tomcat-creds']) {
                    //sh "scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.31.68:/opt/tomcat9/webapps/"
                    //sh "ssh ec2-user@172.31.31.68 /opt/tomcat9/bin/shutdown.sh"
                    //sh "ssh ec2-user@172.31.31.68 /opt/tomcat9/bin/startup.sh"
                    sh "echo testing"
                }
            }
        }
    }
}
