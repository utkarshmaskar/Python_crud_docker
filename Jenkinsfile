pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t flask-crud-app:latest .'
            }
        }
	stage('Run App') {
   	 steps {
        	echo 'Running the app...'
       		 sh 'docker-compose down'
       		 sh 'docker-compose up -d --build'
    }
}

       
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
