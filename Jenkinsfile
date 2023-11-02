pipeline{

    agent any

    stages{

        stage('Start Grid'){
            steps{
                bat "docker-compose -f grid.yml up"
            }
        }

        stage('Run Tests'){
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