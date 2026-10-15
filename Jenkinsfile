
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/nguyenvanann/devops-test1-vanan.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'HTML/CSS does not require npm dependencies'
            }
        }

        stage('Build') {
            steps {
                bat 'if not exist dist mkdir dist'
                bat 'copy /Y index.html dist\\index.html'
                bat 'copy /Y style.css dist\\style.css'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying website...'
                bat 'if not exist C:\\JenkinsDeploy mkdir C:\\JenkinsDeploy'
                bat 'xcopy /Y /I dist\\* C:\\JenkinsDeploy\\'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESS'
        }
        failure {
            echo 'BUILD FAILED'
        }
    }
}
