pipeline {
    agent any

    

    stages {
        stage('Compile') {
            agent {
                label 'Grd-Mvn'
            }
			steps {
                sh 'gradle clean build'
            }
        }
 
    }   
}

