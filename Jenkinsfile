node{
  
  stage('Prepare tools - env jenkins'){
      // add maven to path (and tools)
      env.PATH = "${tool 'M3'}/bin:${env.PATH}"
      env.PATH = "${tool 'jdk8'}/bin:${env.PATH}"

      cleanWs()
  }

  stage('SCM - git'){
      checkout scm
  }
  
  stage('Build artifacts - java'){
      sh 'mvn clean install '
  }
  
  stage('Docker buiild'){
    sh 'docker build . --tag acr-community:6.0.tag'
  }
  
  
}
