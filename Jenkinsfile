pipeline {
    agent any
    tools {
        maven 'maven363'
    }
    stages {
        stage('git repo & clean') {
            steps {
                sh "rm -rf SparkDummyApplication"
                sh "git clone https://github.com/ps2931/SparkDummyApplication.git"
                sh "mvn clean -f "SparkDummyApplication"
            }
        }
        stage('Compile') { 
            steps {
                sh 'cd SparkWordCount && mvn clean compile' 
            }
        }
        stage('Unit Test') { 
            steps {
                sh 'cd SparkWordCount && mvn clean test'
            }
        }
        stage('Package') { 
            steps {
                sh 'cd SparkWordCount && mvn clean package'
            }
        }
    }
}

