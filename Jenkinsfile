pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Récupération du code depuis Git..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Compilation du projet..."
                // Exemple pour Java/Maven :
                sh 'mvn clean install'
            }
        }

        stage('Tests') {
            steps {
                echo "Exécution des tests..."
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo "Packaging de l’application..."
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo "Déploiement de l’application..."
                // Exemple de déploiement :
                sh 'scp target/app.jar user@server:/opt/app/'
            }
        }
    }

    post {
        success {
            echo "Pipeline exécuté avec succès !"
        }
        failure {
            echo "Le pipeline a échoué !"
        }
    }
}
