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
                stage ('Test python 2.6') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-python2.6"
                        }
                    }
                    steps {
                        junit '**/tests/nosetests.xml'
                        cobertura coberturaReportFile: '**/tests/coverage-jenkins.xml'
                    }
                }
                stage ('Test python 3.5') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-py3.5"
                        }
                    }
                    steps {
                        junit '**/tests/nosetests.xml'
                        cobertura coberturaReportFile: '**/tests/coverage-jenkins.xml'
                    }
                }
                stage ('Test python 3.6') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-py3.6"
                        }
                    }
                    steps {
                        junit '**/tests/nosetests.xml'
                        cobertura coberturaReportFile: '**/tests/coverage-jenkins.xml'
                    }
                }
                stage ('Test python 3.7') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-py3.7"
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