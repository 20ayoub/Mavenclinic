pipeline {
    agent any
    tools {
        maven 'Maven339'
        jdk 'JAVA8'
    }
    stages {
            stage('Publish') {
              steps{
                                nexusPublisher nexusInstanceId: 'nexus', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'target/spring-petclinic-1.5.1.war']], mavenCoordinate: [artifactId: 'spring-petclinic', groupId: 'org.springframework.samples', packaging: 'war', version: '1.5.1']]]
                   }
        }
           
    }
}
