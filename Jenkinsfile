@Library("maddylibs") _
pipeline{
    agent any
    stages{
        stage("maven build"){
            when{
                beanch "master"
            }
            steps{
              sh 'mvn clean package -DskipTests=true'
            }
        }
        stage(" Dev Tomcat Deploy"){
            when{
                 branch "develop"
            }
            steps{
                tomcatDeploy("172.31.32.87","ec2-user","tomcat-dev")
                }   
            }
        }
    }
