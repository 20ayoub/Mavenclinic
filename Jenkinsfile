pipeline {
    agent any
    tools {
        maven 'Maven339'
        jdk 'JAVA8'
    }
    stages {
        stage ('Build') {
            steps {
            bat 'mvn install'
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
			bat 'mvn clean cobertura:cobertura'
            step([$class: 'CoberturaPublisher', autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: '**/coverage.xml', failUnhealthy: false, failUnstable: false, maxNumberOfBuilds: 0, onlyStable: false, sourceEncoding: 'ASCII', zoomCoverageChart: false])
		}
		}
         stage('Generate Documentation and site') {
                 steps{
                        bat 'mvn clean javadoc:javadoc site'
                 }
}
        stage('Generate Jar') {
                 steps{
                        bat 'mvn package'
                 }
}
            
           
    }

            
             stage('Publish') {
                                     steps{

                nexusPublisher nexusInstanceId: 'nexus', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'target/spring-petclinic-1.5.1.jar']], mavenCoordinate: [artifactId: 'pipeline-war', groupId: 'com.pipeline', packaging: 'jar', version: '1.5.1']]]
                                           }
                                  }
           
    }

