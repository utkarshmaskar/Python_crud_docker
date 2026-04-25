pipeline {
    agent { label 'ec2-agent' } 

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
		 sh 'docker volume rm python_crud_application_mysql_data || true'
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
