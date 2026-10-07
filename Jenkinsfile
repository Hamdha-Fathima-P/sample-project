pipeline{
    agent any
    stages{
        stage('checkout'){
            steps{
                deleteDir()
                sh '''
                git clone https://github.com/Hamdha-Fathima-P/sample-project.git
                ls -l /var/www/html
                '''
            }
        }
        stage('deploy'){
            steps{
                sh'''
                cp sample-project/* /var/www/html
                '''
            }
        }
    }
}
