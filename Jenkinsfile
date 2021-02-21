pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage('Package'){
            steps{
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
            post{
            always{
                junit 'target/surefire-reports/*.xml'
            }
        }
        }
    }
}
