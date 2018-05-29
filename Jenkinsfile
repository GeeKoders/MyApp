node('master') {
  stage('clone') {
      git url: 'https://github.com/GeeKoders/MyApp.git',
        credentialsId: '023352b7-fbb9-4ee3-9c9c-5b5d734099cc',
        branch: 'master'
  }

  stage('build') {
    sh 'mvn clean test package'
  }
  
  stage('archive') {
      archiveArtifacts artifacts: 'target/*.jar'
      junit 'target/surefire-reports/*.xml'
  }
}