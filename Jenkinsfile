node{
    stage('SCM'){
        git 'https://github.com/sunnydevops/spring-petclinic.git'
    }
    stage('Build & Package'){
       // sh 'mvn package'
        def mvnHome = tool name: 'maven', type: 'maven'
        sh "${mvnHome}/bin/mvn clean package"
    }
    stage('Artifact'){
        archiveArtifacts 'target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar.original'
    }
    stage('Junit'){
        junit 'target/surefire-reports/*.xml'
    }
}


