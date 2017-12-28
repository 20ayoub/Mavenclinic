pipeline {
    agent any
    tools {
        maven 'Maven339'
        jdk 'JAVA8'
    }
    stages {
        
        stage ('Build') {
            steps {
            bat 'mvn clean install'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
        stage ('JUnit tests'){
		steps{
			bat 'mvn test'
		}
		}
        stage ('Code Coverage'){
		steps{
			bat 'mvn cobertura:cobertura'
		}
		}
    }
}
