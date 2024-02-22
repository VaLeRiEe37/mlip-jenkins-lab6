pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
        	python -m venv mlip
		
        # Activate the virtual environment
        	source mlip/bin/activate

        # Upgrade pip to the latest version
        	pip install --upgrade pip
		
        # Install your project's dependencies
        	pip install pytest numpy pandas scikit-learn
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'

                # TODO fill out the path to conda here
                source mlip/bin/activate

                # TODO Complete the command to run pytest
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