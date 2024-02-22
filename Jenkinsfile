pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                echo 'Setting up Python virtual environment and installing dependencies.'

                # Create a virtual environment named 'mlip' and activate it
                python -m venv mlip || python3 -m venv mlip
                source mlip/bin/activate

                # Upgrade pip and install the required dependencies
                pip install --upgrade pip
                pip install pytest numpy pandas scikit-learn
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                echo 'Running tests with pytest.'

                # Activate the virtual environment
                source mlip/bin/activate

                # Run pytest
                pytest
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                echo 'Deploying the project.'

                # Any deployment steps would go here
                '''
            }
        }
    }
}
