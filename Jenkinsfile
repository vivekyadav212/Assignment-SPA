pipeline {
    agent any 
    stages {
        stage('cloning repo and cleanup ') { 
            steps {
                cleanWs()
                sh "git clone https://github.com/vivekyadav212/Assignment-SPA.git" 
            }
        }
        stage('build') { 
            steps {
                sh "cp -r /var/lib/jenkins/workspace/AUTOMATED_RELEASE_PIPELINE/Assignment-SPA/my-app/* ."
                sh "npm install https://github.com/webpack-contrib/mini-css-extract-plugin"
                sh "npm run build"
            }
        }
        stage('Test') { 
            steps {
                sh "npm test" 
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
