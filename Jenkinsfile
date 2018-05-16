pipeline {
    agent { docker { image 'node:6.3' } }
    stages {
        stage('prep') {
          steps {
            sh 'npm --version'
            echo 'Checking npm version'
          }
        }
        stage('Install') {
          echo "Installing yarn packages"
          sh "npm i"
        }

        stage('Build') {
        // Run the maven build
          if (isUnix()) {
            sh "npm run build --prod"
          } else {
            echo "Can't build"
          }
        }
        stage('Results') {
          echo "Nx Build finished!"
        }
    }
}