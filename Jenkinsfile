pipeline{
   agent any
   tools {
        maven 'Apache Maven 3.6.0'
        jdk 'JDK 9'
   }
   stages {
      stage ('Build Stage'){
         steps{
               bat "mvn clean install"
         }
      }

      stage ('Deploy Stage'){
         steps{
               sshagent (['tomcat-dev']){
                  sh "scp -o StrictHostKeyChecking=no target/*.war kamransaeed@192.168.206.131:/var/lib/tomcat8/webapps"
               }
         }
      }
   }
}