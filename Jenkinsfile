pipeline {
    agent any

    stages{
        stage('repo') {
            steps {
                echo "git clone"
                sh "id"
            }
        }
        
        stage('build') {
            steps {
                sh "echo build"
            }
        }
        
        stage('test') {
            steps {
                sh "echo test"
            }
        }
        
        
        stage('approve') {
            when {
                branch 'main'
            }
            agent none
            steps {
                script {
                    timeout(time: 5, unit: 'MINUTES') {
                        input message: 'Aprobar el despliegue', submitter: 'admin'
                    }
                }
            }
        }
        
        stage('deploy') {
            when {
                branch 'main'
            }
            steps {
                sh "echo deploy"
            }
        }
    }
}
