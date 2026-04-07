pipeline {
        agent any
    
        stages {
    
            stage('Build') {
                steps {
                    dir('MCP_Reports_Pro') {
                        bat 'mvn clean compile'
                    }
                }
            }
    
            stage('Test') {
                steps {
                    dir('MCP_Reports_Pro') {
                        bat 'mvn test'
                    }
                }
            }
    
            stage('Report') {
                steps {
                    dir('MCP_Reports_Pro') {
                                           publishHTML([
                            reportDir: 'Report',
                            reportFiles: 'ExtentReport.html',
                            reportName: 'Test Report'
                        ])
                    }
                }
            }
        }
    }
