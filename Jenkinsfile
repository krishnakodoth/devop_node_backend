pipeline {
    agent {
        docker {
            image 'node:18'
            args '-u root'
        }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Backend') {
            steps {
                sh 'node index.js &'
            }
        }
    }
}
