pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
		python -m venv mlip
		
		source mlip/bin/activate

		pip install --upgrade pip
		
		pip install python pytest numpy pandas scikit-learn
		
		echo 'Environment setup is complete and dependencies are installed.'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                echo 'Test Step: We run testing tool like pytest here'

                # TODO fill out the path to conda here
                source mlip/bin/activate

		pytest

                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
