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
            sshagent (['fd12b04e-b9b7-4510-a70f-c5ca5966ee6f']){
               sh "scp -o StrictHostKeyChecking=no target/*.war kamransaeed@192.168.206.131:/var/lib/tomcat8/webapps"
            }
         }
      }
   }
}