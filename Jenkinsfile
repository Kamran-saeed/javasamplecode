pipeline{
   agent any
   tools {
        maven 'Apache Maven 3.6.0'
        jdk 'JDK 9'
   }
   stages {
      stage ('Compile Stage'){
         steps{
               bat "mvn clean install"
         }
      }
   }
}