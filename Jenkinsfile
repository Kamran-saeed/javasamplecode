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
            sshagent (['0a0cc2d6-2996-41c2-9f86-2c20753610d9']){
               sh "scp -o StrictHostKeyChecking=no target/*.war kamransaeed@192.168.206.131:/var/lib/tomcat8/webapps"
            }
         }
      }
   }
}