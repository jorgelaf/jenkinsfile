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
	}
}
