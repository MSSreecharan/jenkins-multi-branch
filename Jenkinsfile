node ('built-in'){
    stage ('Continuous Download')
    {
        git 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
    }
stage('Contnuous Build')
   {
    sh 'mvn package'
   }
   stage ('Continuous Deployement')
   {
       sh 'scp /home/ubuntu/.jenkins/jobs/scripted2/workspace/target/maven-web-application.war ubuntu@ip-172-31-31-75:/var/lib/tomcat9/uapp.war'
   }
   stage ('Continuous Tesing')
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh 'java -jar /home/ubuntu/.jenkins/jobs/scripted2/workspace/testing.jar'
   }
   stage('Continuous Delivery')
   {
     sh 'scp /home/ubuntu/.jenkins/jobs/scripted2/workspace/target/maven-web-application.war ubuntu@ip-172-31-16-100:/var/lib/tomcat9/uuap.war'
   }
}
