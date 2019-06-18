pipeline {
    agent any 
    stages {
        stage('cleanup & cloning repo') { 
            steps {
                cleanWs()
                sh "git clone https://github.com/vivekyadav212/Assignment-SPA.git" 
            }
        }
        stage('build') { 
            steps {
                sh "cp -r /var/lib/jenkins/workspace/AUTOMATED_RELEASE_PIPELINE/Assignment-SPA/my-app/* ."
                sh "npm run build"
            }
        }
        stage('Test') { 
            steps {
                sh "CI=true npm test"
            }
        }
         stage('Deploy') { 
            steps {
                sh "npm install -g serve"
                sh "serve -s build"
            }
        }
    }
}
