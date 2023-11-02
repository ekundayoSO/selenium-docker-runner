pipeline{

    agent any

    stages{

        stage('Start Grid & Run Test'){
            steps{
                bat "docker-compose -f test-suites.yml up"
            }
        }

        stage('Bring Grid Down'){
            steps{
                bat "docker-compose -f test-suites.yml down"
            }
        }

    }

    post{
        always{
             bat "docker system prune -f"
        }
    }
}