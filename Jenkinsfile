pipeline{
    agent any
      tools{
          maven 'Maven'
      }
       stages{
           stage("Test"){
               steps{
                   echo "Test Stages"
                   sh 'mvn test'
               }
           }
           stage("Build"){
               steps{
                   echo "Test Stages"
                   sh 'mvn package'
               }
           }
           stage("Deploy to test env"){
               steps{
                   echo "Test Stages"
                   deploy adapters: [tomcat9(credentialsId: '123', path: '', url: 'http://3.81.121.220:8080')], contextPath: '/app', war: '**/*.war'
               }
           }
           stage("Deploy to prod env"){
               steps{
                   echo "Test Stages"
                   deploy adapters: [tomcat9(credentialsId: '123', path: '', url: 'http://54.227.168.80/:8080')], contextPath: '/app', war: '**/*.war'
               }
           }
       }
}
