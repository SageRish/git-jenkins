pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo 'Building the project with Maven'
                echo 'BUILD SUCCESS'
            }
        }
        stage('Test'){
            steps{
                echo 'Testing the project'
                echo 'Running Unit Tests in JUnit'
                echo 'Running Integration Tests in TestNG'
            }
            post{
                success{
                    emailext to: "s222458666@gmail.com",
                    subject: "Testing Status",
                    body: "Testing was successful",
                    attachLog: true
                }
                failure{
                    emailext to: "s222458666@gmail.com",
                    subject: "Testing Status",
                    body: "Testing detected errors",
                    attachLog: true
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo 'Running SonarQube'
                echo 'SonarQube Analysis Completed'
            }
        }
        stage('Security Scan'){
            steps{
                echo 'Running OWASP ZAP'
                echo 'Security Scan Completed'
            }
            post{
                success{
                    emailext to: "s222458666@gmail.com",
                    subject: "Testing Status",
                    body: "Security Scan was successful",
                    attachLog: true
                }
                failure{
                    emailext to: "s222458666@gmail.com",
                    subject: "Testing Status",
                    body: "Security Scan detected vulnerabilities",
                    attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Use AWS CLI to deploy to Staging EC2 Instance'
                echo 'Deployed to Staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging'
                echo 'Integration Tests Passed'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Use AWS CLI to deploy to Production EC2 Instance'
                echo 'Deployed to Production'
            }
        }
    }
}
