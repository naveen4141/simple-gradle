pipeline {
    agent any

    

    stages {
        stage('Compile') {
            steps {
                gradle('clean', 'classes')
            }
        }
        stage('Unit Tests') {
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
            steps {
                gradle('assemble')
                stash includes: '**/build/libs/*.war', name: 'app'
            }
        }
        
}


