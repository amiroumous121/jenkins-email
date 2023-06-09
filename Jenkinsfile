


pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Use a build tool (e.g., Maven, Gradle, or Node.js)
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Use test automation tools (e.g., JUnit, TestNG, or Mocha)
            }
            post {
                success {
                    script {
                        def emailAddress = 'hesi.zandiyeh@gmail.com'
                        def emailSubject = "Success: Unit and Integration Tests - Pipeline '${env.JOB_NAME}' (${currentBuild.displayName})"
                        def emailBody = "Pipeline status: ${currentBuild.currentResult}"
                        println "Sending email to: ${emailAddress}"
                        println "Subject: ${emailSubject}"
                        println "Body: ${emailBody}"
                        emailext (
                            to: emailAddress,
                            subject: emailSubject,
                            body: emailBody,
                            mimeType: 'text/html',
                            attachLog: true
                        )
                    }
                }
                failure {
                    script {
                        def emailAddress = 'hesi.zandiyeh@gmail.com'
                        def emailSubject = "Failure: Unit and Integration Tests - Pipeline '${env.JOB_NAME}' (${currentBuild.displayName})"
                        def emailBody = "Pipeline status: ${currentBuild.currentResult}"
                        println "Sending email to: ${emailAddress}"
                        println "Subject: ${emailSubject}"
                        println "Body: ${emailBody}"
                        emailext (
                            to: emailAddress,
                            subject: emailSubject,
                            body: emailBody,
                            mimeType: 'text/html',
                            attachLog: true
                        )
                    }
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                // Integrate code analysis tools (e.g., SonarQube or Checkstyle)
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Starting security scan...'
                // Perform security scan (e.g., OWASP Dependency-Check or Snyk)
            }
            post {
                success {
                    script {
                        def emailAddress = 'hesi.zandiyeh@gmail.com'
                        def emailSubject = "Success: Security Scan - Pipeline '${env.JOB_NAME}' (${currentBuild.displayName})"
                        def emailBody = "Pipeline status: ${currentBuild.currentResult}"
                        println "Sending email to: ${emailAddress}"
                        println "Subject: ${emailSubject}"
                        println "Body: ${emailBody}"
                        emailext (
                            to: emailAddress,
                            subject: emailSubject,
                            body: emailBody,
                            mimeType: 'text/html',
                            attachLog: true
                        )
                    }
                }
                failure {
                    script {
                        def emailAddress = 'hesi.zandiyeh@gmail.com'
                        def emailSubject = "Failure: Security Scan - Pipeline '${env.JOB_NAME}' (${currentBuild.displayName})"
                        def emailBody = "Pipeline status: ${currentBuild.currentResult}"
                        println "Sending email to: ${emailAddress}"
                        println "Subject: ${emailSubject}"


println "Body: ${emailBody}"
                        emailext (
                            to: emailAddress,
                            subject: emailSubject,
                            body: emailBody,
                            mimeType: 'text/html',
                            attachLog: true
                        )
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Deploy to staging server (e.g., AWS EC2 instance)
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Run integration tests on staging environment
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
                // Deploy to production server (e.g., AWS EC2 instance)
            }
        }
    }

    post {
        always {
            script {
                def emailAddress = 'hesi.zandiyeh@gmail.com'
                def emailSubject = "Pipeline '${env.JOB_NAME}' (${currentBuild.displayName})"
                def emailBody = "Pipeline status: ${currentBuild.currentResult}"
                println "Sending email to: ${emailAddress}"
                println "Subject: ${emailSubject}"
                println "Body: ${emailBody}"
                emailext (
                    to: emailAddress,
                    subject: emailSubject,
                    body: emailBody,
                    mimeType: 'text/html',
                    attachLog: true
                )
            }
        }
    }
}


