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
                ls -l 
                '''
                stash name : 'website' , includes : 'sample-project/**'
            }
        }
        stage('deploy'){
            agent{
                label 'deployagent'
            }
            steps{
                deleteDir()
                unstash 'website'
                sh'''
                sudo cp -r sample-project/* /var/www/html
                ls -l /var/www/html
                '''
            }
        }
    }
}
