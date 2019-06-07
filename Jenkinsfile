pipeline {
    agent any
    parameters
            {
                choice(
                        choices: ['DEV', 'TST2', 'TST1', 'ACC', 'PROD'],
                        description: 'Choose your environment to deploy',
                        name: 'PARAM_ENV_DEPLOY')
            }
    stages {
        stage('Build') {
            when {
                expression { params.PARAM_ENV_DEPLOY == 'DEV' }
            }
            stages {
                stage('Building Distributable Package') {
                    steps {
                        echo "${params.PARAM_ENV_DEPLOY}"
                        echo 'Building'
                    }
                }
                stage('Testing Distributable Package') {
                    steps {
                        echo 'Testing'
                    }
                }
                stage('Archiving Distributable Package') {
                    steps {
                        echo 'Archiving'
                    }
                }
            }
        }
        stage('environment') {
            parallel {
                stage('1. Dev Deployment') {
                    when {
                        expression { params.PARAM_ENV_DEPLOY == 'DEV' }
                    }
                    stages {
                        stage('Deploy') {
                            steps {
                                echo 'Deploy To DEV'
                            }
                        }
                        stage('Smoke test') {
                            steps {
                                echo 'Smoke test'
                            }
                        }
                    }
                }
                stage('2. TST2 Deployment') {
                    when {
                        expression { params.PARAM_ENV_DEPLOY == 'TST2' }
                    }
                    stages {
                        stage('Deploy') {
                            steps {
                                echo 'Deploy To TST2'
                            }
                        }
                        stage('Smoke test') {
                            steps {
                                echo 'Smoke test'
                            }
                        }
                    }
                }
                stage('3. TST1 Deployment') {
                    when {
                        expression { params.PARAM_ENV_DEPLOY == 'TST1' }
                    }
                    stages {
                        stage('Deploy') {
                            steps {
                                echo 'Deploy To TST1'
                            }
                        }
                        stage('Smoke test') {
                            steps {
                                echo 'Smoke test'
                            }
                        }
                    }
                }
                stage('4. ACC Deployment') {
                    when {
                        expression { params.PARAM_ENV_DEPLOY == 'ACC' }
                    }
                    stages {
                        stage('Deploy') {
                            steps {
                                echo 'Deploy To ACC'
                            }
                        }
                        stage('Smoke test') {
                            steps {
                                echo 'Smoke test'
                            }
                        }
                    }
                }
                stage('5. PROD Deployment') {
                    when {
                        expression { params.PARAM_ENV_DEPLOY == 'PROD' }
                    }
                    stages {
                        stage('Deploy') {
                            steps {
                                echo 'Deploy To PROD'
                            }
                        }
                        stage('Smoke test') {
                            steps {
                                echo 'Smoke test'
                            }
                        }
                    }
                }
            }
        }
    }
}
