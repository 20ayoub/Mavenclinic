pipeline {
    agent any
    tools {
        maven 'Maven339'
        jdk 'JAVA8'
    }
    stages {
         stage('Generate Javadocs') {
                 steps{
                        bat 'mvn javadoc:javadoc'
                 }
        }
    }
}
