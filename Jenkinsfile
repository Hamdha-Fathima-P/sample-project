pipeline{
    agent none
    stages{
        stage('build'){
            agent{
                label 'buildagent'
            }
            steps{
                deleteDir()
                sh '''
                git clone https://github.com/Hamdha-Fathima-P/sample-project.git
                ls -l /var/www/html
                '''
                stash name : 'website' , includes : 'sample-project/**'
            }
        }
        stage('deploy'){
            agent{
                label 'deployagent'
            }
            steps{
                unstash 'website'
                sh'''
                sudo cp sample-project/* /var/www/html
                '''
            }
        }
    }
}

