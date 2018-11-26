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

      // stage ('Deploy Stage'){
      //    steps{
      //       sshagent (['0a0cc2d6-2996-41c2-9f86-2c20753610d9']){
      //          sh "scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.44.82:/home/"
      //       }
      //    }
      // }
   }
}