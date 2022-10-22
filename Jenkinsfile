pipeline {
    agent { label 'py3.9' }
    stages {
        stage('vcs') {
            steps {
                git branch: 'master', url:'https://github.com/srvarri/python-webcount.git'
            }

        }
        stage('build') {
            steps {
                sh ' requirements.txt'
                sh 'tox'
            }
        }

        stage('test reports') {
            steps {
                junit 'junit-py39.xml'
            }
        }
    }
}            