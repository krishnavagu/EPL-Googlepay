pipeline {
    agent any 
    stages {
        stage('Git Hub') { 
            steps {
                echo"Build stage"
                git credentialsId: 'GITHUB', url: 'https://github.com/krishnavagu/EPL-Googlepay.git'
            }
        }
        stage('Build') { 
            steps {
                echo"Test Stage"
                sh label: '', script: 'mvn clean package'
            }
        }
        stage('Deploy') { 
            steps {
                echo"Deploy stage"
                deploy adapters: [tomcat9(credentialsId: 'Tomcat', path: '', url: 'http://54.90.103.92:8085/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
