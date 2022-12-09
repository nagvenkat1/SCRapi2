pipeline {
    agent {label 'DOCKER'}
    triggers { pollSCM('* * * * *') }
    stages {
        stage ('vcs') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/nagvenkat1/SCRapi2.git'
            }
        }
        stage ('docker push') {
            steps {
                sh 'git clone https://github.com/DevProjectsForDevOps/StudentCoursesRestAPI.git'
                sh 'cd StudentCoursesRestAPI'
                sh 'docker image build -t studentcoursesrestapi:1.0 .'
                sh 'docker image tag studentcoursesrestapi:1.0 nagvenkat/studentcoursesrestapi:1.0'
                sh 'docker image push nagvenkat/studentcoursesrestapi:1.0'
                sh 'docker container run --name scr -d -p 8082:8080 nagvenkat/studentcoursesrestapi:1.0'
           
            }
        }
