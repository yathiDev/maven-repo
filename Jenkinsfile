pipeline {
    // add your slave label name
    agent { label 'my_maven_slave'}
    tools{
        maven 'maven-test'
    }
    stages {
        stage ('Checkout_SCM') {

            steps {
          	    
	     checkout scm
            }
        }

        stage ('Maven_Build') {

            steps {
               sh 'mvn clean package'
            }
        }
        
        stage ('Deploy_Tomcat') {

            steps {
              sh "sudo scp target/maven-web-application.war  ec2-user@54.83.187.138:/opt/tomcat9/webapps/"
         }
        }
        
    }
}
