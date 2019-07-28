node{
    stage('SCM'){
        git 'https://github.com/sunnydevops/spring-petclinic.git'
    }
    stage('Build & Package'){
        def mvnHome = tool name: 'maven', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
    stage('artifactory'){
        archiveArtifacts 'petclinic-pipeline/target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar.original'
    }
    stage('Junit'){
        junit 'petclinic-pipeline/target/surefire-reports/*.xml'

    }
}