pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '88d169fe-219e-45cf-90b3-b19def7df08d', path: '',
               url: 'http://ec2-3-235-163-131.compute-1.amazonaws.com:8080/')],
               contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
