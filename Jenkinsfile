pipeline {
    agent {
        docker { image 'srinivasger/amazonlinux-with-custodian' }
    }
    stages {
        stage('Load virtualenvironment') {
            steps {
                sh "source /app/bin/activate"
            }
        }
        stage('Test') {
            steps {
                sh "AWS_DEFAULT_REGION=us-west-1 custodian run --output-dir=. check-empty-tag.yml"
            }
        }
    }
}
