pipeline {
 	agent any 
	stages { 
		stage('Compilar') { 
			steps { 
				script {
					sh 'pwd'
					sh 'mvn package'
				}
				echo 'compilado correcto'
			}
		}
		stage('Analisis') {
			steps {
				escaner = tool 'misonar'
			}
			withSonarQubeEnv('misonar') { 
				sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=pruebajenkinssonar -Dsonar.projectVersion=1.0 -Dsonar.sources=./src" }
		}
	}
}
