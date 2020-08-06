pipeline {
    agent {
        label 'slave01'
    }
    options {
        checkoutToSubdirectory('B2HANDLE')
    }
    environment {
        PROJECT_DIR="B2HANDLE"
    }
    stages {
        stage ('Python setup') {
            parallel {
                stage ('Test python 2.7') {
                    agent {
                        dockerfile {
                            filename "Dockerfile"
                            dir "$PROJECT_DIR"
                            additionalBuildArgs "-t eudat-b2handle"
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
                            additionalBuildArgs "-t eudat-b2handle:python2.6"
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
                            additionalBuildArgs "-t eudat-b2handle:py3.5"
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
                            additionalBuildArgs "-t eudat-b2handle:py3.6"
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
                            additionalBuildArgs "-t eudat-b2handle:py3.7"
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
        stage ('Run tests') {
            parallel {
                stage ('Test python 2.7') {
                    agent {
                        dockerfile {
                            filename "Dockerfile"
                            dir "$PROJECT_DIR/b2handle/tests"
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
                            dir "$PROJECT_DIR/b2handle/tests"
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
                            dir "$PROJECT_DIR/b2handle/tests"
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
                            dir "$PROJECT_DIR/b2handle/tests"
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
                            dir "$PROJECT_DIR/b2handle/tests"
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