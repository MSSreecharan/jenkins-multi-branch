node ('built-in'){
    stage ('Continuous Download_loans')
    {
        git 'https://github.com/lillysree/jenkins-multi-branch.git'
    }
stage('Contnuous Build_loans')
   {
    sh 'mvn package'
   }
   stage ('Continuous Deployement_loans')
   {
       sh 'scp /home/ubuntu/.jenkins/jobs/scripted2/workspace/target/maven-web-application.war ubuntu@ip-172-31-31-75:/var/lib/tomcat9/uapp.war'
   }
   stage ('Continuous Tesing_loans')
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh 'java -jar /home/ubuntu/.jenkins/jobs/scripted2/workspace/testing.jar'
   }
   stage('Continuous Delivery_loans')
   {
     sh 'scp /home/ubuntu/.jenkins/jobs/scripted2/workspace/target/maven-web-application.war ubuntu@ip-172-31-16-100:/var/lib/tomcat9/uuap.war'
   }
}
