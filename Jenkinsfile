node{
    stage('SCM'){
        git 'https://github.com/sunnydevops/spring-petclinic.git'
    }
    stage('Build & Package'){
        def mvnHome = tool name: 'maven', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
}