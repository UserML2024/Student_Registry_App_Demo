pipeline{
    agent any

    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/UserML2024/Student_Registry_App_Demo.git'
            }
        }
        stage('Install dependencies'){
            steps{
                script{
                    
                        bat 'npm install'
                }
            }
        }
        stage("Start app and run tests"){
            steps{
                script{
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8090'
                    bat 'npm test'
                }
            }
        }

    }

    post{
        always{
            echo "CI pipeline completed"
        }
    }
}