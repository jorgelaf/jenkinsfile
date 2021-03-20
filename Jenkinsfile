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
				script {
					scannerHome = tool 'miescaner'
				}
				withSonarQubeEnv('misonar') { 
					sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=pruebajenkinssonar -Dsonar.projectVersion=1.0 -Dsonar.sources=./ -Dsonar.java.binaries=./target/classes -Dsonar.login=admin -Dsonar.password=admin1" }
			}
			
		}
	}
}
