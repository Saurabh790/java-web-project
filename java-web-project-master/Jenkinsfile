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
                deploy adapters: [tomcat7(credentialsId: '3c7715c5-eb8a-48d1-ab79-aef1b35753be', path: '',
                url: 'http://ec2-3-216-23-127.compute-1.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
