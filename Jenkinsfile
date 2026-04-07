pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/janhavivi3101-sketch/Selenium_Grid_Project.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Report') {
            steps {
                publishHTML(target:[
                    allowMissing: false,
                    alwasysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: 'target',
                    reportFiles: 'extent-report.html',
                    reportName: 'Test Report'
                ])
            }
        }
    }
}
