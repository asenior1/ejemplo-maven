pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                dir('/Users/edgarramirez/Documents/Andrea/ejemplo-maven'){
                    sh './mvnw clean compile -e'
                }
            }
        }
        stage('Test') {
            steps {
                dir('/Users/edgarramirez/Documents/Andrea/ejemplo-maven'){
                    sh './mvnw clean test -e'
                }
            }
        }
        stage('Jar') {
            steps {
                dir('/Users/edgarramirez/Documents/Andrea/ejemplo-maven'){
                    sh './mvnw clean package -e'
                }
            }
        }
        stage('Run') {
            steps {
                dir('/Users/edgarramirez/Documents/Andrea/ejemplo-maven'){
                    sh 'nohup bash mvnw spring-boot:run &'
                    //sh './mvnw spring-boot:run'
                }
            }
        }
        stage('Testing') {
            steps {
                dir('/Users/edgarramirez/Documents/Andrea/ejemplo-maven'){
                    sleep 10
                    sh 'curl http://localhost:8081/rest/mscovid/estadoMundial'
                    //script{
                        //sh 'curl -X GET 'http://localhost:8080/rest/mscovid/test?msg=testing''
                        //final String url = "http://localhost:8080/rest/mscovid/test?msg=testing"
                        //final String response = sh(script: "curl -s $url", returnStdout: true).trim()
                        //echo response
                    //}
                }
            }
        }
    }
}
