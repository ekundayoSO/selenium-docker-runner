pipeline{

    agent any

    stages{

        stage('Start Grid & Run Test'){
            steps{
                bat "docker-compose -f grid.yml up -d"
            }
        }

        stage('Bring Grid Down'){
            steps{
                bat "docker-compose -f test-suites.yml up"
            }
        }

    }

    post{
        always{
             bat "docker-compose -f grid.yml down"
             bat "docker-compose -f test-suites.yml down"
        }
    }
}