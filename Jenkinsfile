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
        post {
            always {
            script {
                currentBuild.result = currentBuild.result ?: 'SUCCESS'
            }
            emailext(
                to: 'sanka.mapalagama@gmail.com',
                subject: "Jenkins Pipeline - ${currentBuild.fullDisplayName} - ${currentBuild.result}",
                body: """
                    <p>Build Result: ${currentBuild.result}</p>
                    <p>Build URL: <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>
                """,
                attachLog:true,
                mimeType: 'text/html'
            )
        }
        success {
            echo 'Build was successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }

        }
        stage("Test 1"){
            steps{
                echo "Testing....."
            }
        }   
            
               
    }
}
