pipeline {
    agent any

    stages {
        stage('Run Script') {
            steps {
                script {
                    // Run a shell command and save output to a file
                    sh '''
                        echo "Running my custom logic..." > output.txt
                        echo "Timestamp: $(date)" >> output.txt
                    '''
                }
            }
        }

        stage('Archive Artifact') {
            steps {
                // Save output.txt as a build artifact
                archiveArtifacts artifacts: 'output.txt', fingerprint: true
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}

