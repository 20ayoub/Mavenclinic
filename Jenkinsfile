pipeline {
    agent any
    tools {
        maven 'Maven339'
        jdk 'JAVA8'
    }
    stages {
            stage('Publish') {
                                     steps{

                nexusPublisher nexusInstanceId: 'nexus', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'E:\Program files\Jenkins\workspace\pipeline\target\spring-petclinic-1.5.1.war']], mavenCoordinate: [artifactId: 'pipeline-war', groupId: 'com.pipeline', packaging: 'war', version: '1.0']]]
                                     }
        }
           
    }
}
