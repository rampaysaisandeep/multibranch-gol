pipeline {
    agent {label 'gameoflife'}
    triggers {
        pollSCM('* * * * *')
    }
    options {
        timeout(time: 30, unit: 'MINUTES')
    }
    parameters {
        string(name: 'MAVENGOAL', defaultValue: 'clean package', description: 'Given maven goal')
    }
    stages{
        stage('SCM'){
            steps {
                git 'https://github.com/rampaysaisandeep/multibranch-gol.git'
            }
        }
        stage('Build'){
            steps {
                sh script: "mvn ${params.MAVENGOAL}"
            }
        }
    }
}