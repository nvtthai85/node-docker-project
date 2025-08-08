pipeline {
  agent any 
  
  stages {
    stage("Checkout") {
      steps {
        checkout scm
      }
    }
    
    stage("Setup Node.js") {
      steps {
        // Sử dụng nvm hoặc công cụ quản lý phiên bản Node.js
        sh '''
          curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
          export NVM_DIR="$HOME/.nvm"
          [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
          nvm install 18  # Chọn phiên bản Node.js bạn cần
          node --version
        '''
      }
    }
    
    stage("Install Dependencies") {
      steps {
        sh 'npm ci'  // Sử dụng npm ci thay vì npm install cho CI
      }
    }
    
    stage("Test") {
      steps {
        sh 'npm test'
      }
    }

    stage("Build") {
      steps {
        sh 'npm run build'
      }
    }
  }
}
