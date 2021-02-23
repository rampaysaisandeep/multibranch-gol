pipeline{
    agent {label 'gameoflife'}
    triggers {
        cron('* * * * *')
    }
    stages{
        stage('SCM'){
            steps {
                git 'https://github.com/rampaysaisandeep/multibranch-gol.git'
            }
        stage('BUILD'){
            steps {
                sh 'mvn clean package'
            }
        stage('post build'){
            steps {
                Junit 'gameoflife-web/target/surefire-reports/*.xml'  
            }    
                
        }
    }
}