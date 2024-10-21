pipeline {
    agent any

    triggers {
        // Temporarily disabling polling for testing. Uncomment when using pollSCM.
        cron('* * * * *') 
    }

    stages {
        stage('Récupération du code source') {
            steps {
                // Clone the code source from the Git repository.
                git branch: 'main', url: 'https://github.com/MohamedAliNaguez/mavenproj.git'
            }
        }

        stage('Affichage de la date système') {
            steps {
                // Display the current system date.
                script {
                    def date = new Date()
                    echo "La date actuelle est : ${date}"
                }
            }
        }
    }

    post {
        success {
            echo 'Build terminé avec succès.'
        }
        failure {
            echo 'Le build a échoué.'
        }
    }
}
