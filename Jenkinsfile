pipeline {
 agent {label 'DOCKER'}
 stages {
    stage('clone') {
        steps {
            git url: 'https://github.com/nagvenkat1/SCRapi2.git',
            branch: 'main'

        }
    }
    stage('build') {
        steps {
            sh 'sh Docker.sh'

        }
    }
 }
}
