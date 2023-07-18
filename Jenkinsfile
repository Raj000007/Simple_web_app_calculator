pipeline {
    agent any
    tools {
        maven "MAVEN_HOME"
    }
    environment {
        SNAP_REPO = 'snapshot'
  NEXUS_USER = 'admin'
  NEXUS_PASS = 'admin'
  RELEASE_REPO = 'release'
  CENTRAL_REPO = 'central'
  NEXUSIP = '18.212.185.211'
  NEXUSPORT = '8081'
  NEXUS_GRP_REPO = 'group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}
