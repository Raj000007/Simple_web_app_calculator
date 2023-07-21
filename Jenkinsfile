pipeline {
    agent any
    tools {
        maven "MAVEN_HOME"
        
    }
    
    environment {
        SNAP_REPO = 'vprofile-snapshot'
  NEXUS_USER = 'admin'
  NEXUS_PASS = 'admin'
  RELEASE_REPO = 'release'
  CENTRAL_REPO = 'central'
  NEXUSIP = '54.196.137.6'
  NEXUSPORT = '8081'
  NEXUS_GRP_REPO = 'group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post {
                success {
                    echo "Now Archiving."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }

        stage('Test'){
            steps {
                sh 'mvn -s settings.xml test'
            }

        }

        stage('Checkstyle Analysis'){
            steps {
                sh 'mvn -s settings.xml checkstyle:checkstyle'
            }
        }
    }
}
