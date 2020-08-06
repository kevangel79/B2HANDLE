pipeline {
    agent any
    options {
        checkoutToSubdirectory('B2HANDLE')
    }
    environment {
        PROJECT_DIR="B2HANDLE"
    }
    stages {
        stage ('Test') {
            parallel {
                stage ('Test python 2.7') {
                    agent {
                        dockerfile {
                            filename "Dockerfile"
                        }
                    }
                    steps {
                        junit '**/tests/nosetests.xml'
                        cobertura coberturaReportFile: '**/tests/coverage-jenkins.xml'
                    }
                }
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
} 