pipeline {

   agent any

 

   stages {
    stage('Build') {

         steps {

            // Get some code from a GitHub repository

            git 'https://github.com/ashish447/Angular7-Spring-boot/'
B




	sh "test"
		

            sh "chmod 777 mvnw"  
            sh  "mvn -v"
            // Run Maven on a Unix agent.

            sh "mvn  -Dmaven.test.failure.ignore=true clean package -DskipTest"


            // To run Maven on a Windows agent, use

            // bat "mvn -Dmaven.test.failure.ignore=true clean package"

         }


         post {

            // If Maven was able to run the tests, even if some of the test

            // failed, record the test results and archive the jar file.

            success {

               junit '**/target/surefire-reports/TEST-*.xml'

               archiveArtifacts 'target/*.jar'

            }

         }

      }

   }

}
