pipeline{
   agent any
   tools {
        maven 'Apache Maven 3.6.0'
        //jdk 'JDK 9'
   }
   stages {
      stage ('Build Stage'){
         steps{
            sh "mvn clean install"
         }
      }

      stage ('Deploy Stage'){
         steps{
            sshagent (['5af10662-4c3e-4ac6-8ed0-1799eb35db86']){
               sh "scp -o StrictHostKeyChecking=no target/*.war kamransaeed@192.168.206.131:/var/lib/tomcat8/webapps"
            }
         }
      }
   }
}