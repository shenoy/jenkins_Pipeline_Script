pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent any 
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    agent any
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
