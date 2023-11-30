pipeline{
    agent any
    options {
        timeout(time:1,units:'hour')
    }
    triggers{
        pollSCM('* * * * *')
    }
    stages{
        stage('sorce code'){
            steps{
                git url:'',
                    branch:''
            }
        }
        stage('mvngoal'){
            steps{
                sh script: 'mvn clean package'
            }
        }
    }
    stages{
        stage('publish'){
            steps{
                junit testResults: '**/surefire-reports/TEST-*.xml'
                archiveArtifacts artifacts: '**/target/gameoflife.war'
            }
        }
    }
}