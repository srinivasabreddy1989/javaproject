pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps {
                //checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-creds', url: 'https://github.com/srinivasabreddy1989/javahomehiring.git']])
                git branch: 'develop', credentialsId: 'git-creds', url: 'https://github.com/srinivasabreddy1989/javaproject.git'
            }
        }
        stage('Git package') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Apache deploy') {
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
