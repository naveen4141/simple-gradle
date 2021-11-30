pipeline {
    agent any

    

    stages {
        stage('Compile') {
            agent {
                label 'Grd-Mvn'
            }
			steps {
                gradle('clean', 'classes')
            }
        }
        stage('Unit Tests') {
            agent {
                label 'Grd-Mvn'
            }
			steps {
                gradle('test')
            }
            post {
                always {
                    junit '**/build/test-results/test/TEST-*.xml'
                }
            }
        }
        stage('Assemble') {
            agent {
                label 'Grd-Mvn'
            }
			steps {
                gradle('assemble')
                stash includes: '**/build/libs/*.war', name: 'app'
            }
        }
    }   
}


