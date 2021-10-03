pipeline {
    agent any
    stages {
        stage('Example Build') {
            enivronment { 
           AWS_ACCESS_KEY_ID = credentials('jenkins_aws_secret_key_id')
           AWS_SECRET_ACCESS_KEY = credentials('jenkins_aws_secret_access_keyid')
            }
            steps {
                echo 'Hello World'
                sh 'kubectl create deployment nginx-deployment --image=nginx'
            }
        }
        stage('Example Deploy') {
            when {
                branch 'production'
                environment name: 'DEPLOY_TO', value: 'production'
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
