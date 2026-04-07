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
                    dir('Report') {
                                           publishHTML([
                            reportDir: 'Report_dir',
                            reportFiles: 'ExtentReport.html',
                            reportName: 'Test Report'
                        ])
                    }
                }
            }
        }
    }
