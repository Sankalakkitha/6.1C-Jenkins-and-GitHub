pipeline{
    agent any

    stages{
        stage('Build'){
            steps{
                //Automation tool : Maven
                echo"Building"
            }
        }
         stage('Unit and Integration Tests'){
            steps{
                //Unit Test	   : JUnit
                //Integration Test   : Surefire Plugin
                echo"Testing"

            }
        }
         stage('Code Analysis'){
            steps{
                //Code Analysis Tools : SonarQube   (Checkstyle,FindBugs)
                echo"Code Analysing"
            }
        } 
        stage('Security Scan'){
            steps{
                //SonarQube
                //Checkmarx
                echo"Code vulnerability detection through security scans"
            }
        }  
        stage('Deploy to Staging'){
            steps{
                //AWS CLI to deploy to EC2
                echo"deploy the application to a staging server"
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                //Selenium integration tests on the staging environment              
                echo"Deploy the code to the production  environment "
            }
        } 

        stage('Deploy to Production'){
            steps{
                // //AWS CLI            
                echo"Deploy the code to the production  environment "
            }
            post{
                success{
                    subject:"Continuous Integration and Deployment with Jenkins and GitHub",
                    attachLog: true,
                    to: "sanka.mapalagama@gmail.com",
                    body:"Developers Please check build status and deployment events"
                }
            }

        }
        stage("Test case"){
            steps{
                echo "Testing....."
            }
        }           
            
               
    }
}
