pipeline{

    agent any

    stages{

        stage('Start Grid & Run Test'){
            steps{
                bat "docker-compose -f grid.yml -f test-suites.yml up"
            }
        }

        stage('Bring Grid Down'){
            steps{
                bat "docker-compose -f grid.yml -f test-suites.yml down"
            }
        }

    }
}