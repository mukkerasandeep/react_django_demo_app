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
                    sh "docker build  -t react_django_demo_app ."
		}
            }
        }
        stage ('Run'){ 
            steps {
                script {
                    sh "  docker run -p 8001:8001 -d react_django_demo_app"
                }
            }
        }
     }
}
