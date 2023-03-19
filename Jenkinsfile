pipeline { 
    agent any
    stages {
        stage ('Build') {
            steps {
               git branch: 'main', url: 'https://github.com/mukkerasandeep/react_django_demo_app.git'
            }
        }
        stage ('Test') {
            steps {
                echo "Testing"
			}
        }
        stage ('Deploy') {  
            steps {
                script  {
                    sh "sudo docker build --no-cache -t react_django_demo_app ."
				}
            }
        }
        stage ('Run'){ 
            steps {
                script {
                    sh " sudo docker run -p 8001:8001 -d react_django_demo_app"
                }
            }
        }
     }
}
