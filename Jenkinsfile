pipeline {
    agent any
    tools {
        maven 'Maven339'
        jdk 'JAVA8'
    }
    stages {
            
             stage('Publish') {
                                     steps{

                nexusPublisher nexusInstanceId: 'nexus', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'target/spring-petclinic-1.5.1.jar']], mavenCoordinate: [artifactId: 'pipeline-war', groupId: 'com.pipeline', packaging: 'jar', version: '1.5.1']]]
                                     }
        }
            
           
    }
}
