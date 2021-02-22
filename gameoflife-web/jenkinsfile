pipeline {
    agent {gameoflife}
    stages{
        stage(SCM){
            step {
                git https://github.com/rampaysaisandeep/game-of-life.git
            }
        }
        stage(Build){
            step {
                sh script "mvn clean package"
            }
        }
            }
        }
    }
}