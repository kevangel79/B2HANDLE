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
                            dir "$PROJECT_DIR"
                            args "-u root:root"
                        }
                    }
                    steps {
                        sh '''
                            cd $WORKSPACE/$PROJECT_DIR
                            python setup.py install
                        '''
                    }
                }
                stage ('Test python 2.6') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-python2.6"
                            dir "$PROJECT_DIR"
                            args "-u root:root"
                        }
                    }
                    steps {
                        sh '''
                            cd $WORKSPACE/$PROJECT_DIR
                            python setup.py install
                        '''
                    }
                }
                stage ('Test python 3.5') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-py3.5"
                            dir "$PROJECT_DIR"
                            args "-u root:root"
                        }
                    }
                    steps {
                        sh '''
                            cd $WORKSPACE/$PROJECT_DIR
                            python setup.py install
                        '''
                    }
                }
                stage ('Test python 3.6') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-py3.6"
                            dir "$PROJECT_DIR"
                            args "-u root:root"
                        }
                    }
                    steps {
                        sh '''
                            cd $WORKSPACE/$PROJECT_DIR
                            python setup.py install
                        '''
                    }
                }
                stage ('Test python 3.7') {
                    agent {
                        dockerfile {
                            filename "Dockerfile-py3.7"
                            dir "$PROJECT_DIR"
                            args "-u root:root"
                        }
                    }
                    steps {
                        sh '''
                            cd $WORKSPACE/$PROJECT_DIR
                            python setup.py install
                        '''
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