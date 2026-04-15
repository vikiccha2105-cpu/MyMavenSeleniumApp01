pipeline {
    agent any

    tools {
        maven 'MAVEN'   // Ensure this name matches Jenkins Global Tool Config
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/vikiccha2105-cpu/MyMavenSeleniumApp01.git',
                    credentialsId: 'github-creds'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

    }

    post {
        success {
            echo 'Build and testing successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
