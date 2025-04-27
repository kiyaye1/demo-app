pipeline {
    agent any
    
    environment {
        APP_DIR='/var/lib/jenkins/workspace/scripted_pipeline/demo-app'
        JAR_FILE='myapp-0.0.1-SNAPSHOT.jar'
    }

    stages {
        stage('Clean Workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Cloning Git Repo') {
            steps {
                script {
                    sh 'git clone "https://github.com/neerajbalodi/demo-app.git"'
                }
            }
        }
        stage('Build Application') {
            steps {
                script {
                    sh 'cd demo-app && mvn clean install'
                }
            }
        }
        stage('Run Application') {
            steps {
                script {
                    sh 'cd $APP_DIR/target'
                }
            }
        }
    }
}
