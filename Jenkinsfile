pipeline {
    agent any
    tools { 
        maven 'mvn' 
        jdk 'jdk' 
    }
    stages {
        stage("clone code"){
            steps{
               git credentialsId: 'github', url: 'https://github.com/ravdy/hello-world.git'
            }
        }
        stage("build code"){
            steps{
              sh "mvn clean install"
            }
        }
        stage("deploy"){
            steps{
              echo 'deploying the software'  
              // sshagent(['deploy_user']) {
              //   sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@13.229.183.126:/opt/apache-tomcat-8.5.55/webapps" 
              //  }
            }
        }
    }
}
