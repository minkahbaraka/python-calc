pipeline {
    agent any
    // triggers {
    //      pollSCM('* * * * *')
    // }
     // added comment here to test polling
     // added another comment to test polling since the above didn't work
     //after manual build this worked too good
    stages {
        stage ("Checkout") {
            steps {
                git url: 'https://github.com/minkahbaraka/python-calc.git'
            }
        }
        

        stage ("Build") {
            steps {
               sh "./python calculator.py"
            }
        }

        stage ("Unit Test") {
            steps {
               sh "./python test_calculator.py"
            }
        }

        
    }

    post {
		        always {
			        script {
				        echo 'Post build'
			}
		}
		        success {
			        script {
				        echo 'Yeah Boi !!!!!'
			}
		}
		        aborted {
			        script {
				        echo 'Aborted'
			}
		}
		        failure {
			        script {
				        echo 'Ugh !!!!'
			}
		}
    }

}
        