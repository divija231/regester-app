pipeline {
    agent any
    tools {
        jdk 'java17'
        maven 'Maven3'
    }
    stages {
        stage("Cleanup workspace") {
            steps {
                cleanWs()
            }
        }
        stage("Checkout from SCM") {
            steps {
                script {
                    // Change to the project directory
                    dir('/var/lib/jenkins/workspace/1234') {
                        git branch: 'main', url: 'https://github.com/divija231/regester-app'
                        sh 'ls -la'
                    }
                }
            }
        }
        stage("Build application") {
            steps {
                script {
                    // Change to the project directory
                    dir('/var/lib/jenkins/workspace/1234') {
                        sh "mvn clean package"
                    }
                }
            }
        }
        stage("Testing application") {
            steps {
                script {
                    // Change to the project directory
                    dir('/var/lib/jenkins/workspace/1234') {
                        sh "mvn test"
                    }
                }
            }
        }
    }
}

