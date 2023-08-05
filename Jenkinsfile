pipeline {
  agent any
  parameters {
    choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description:'')
    booleanParam(name:'executetests', defaultvalue: true, description'')
  }
  stages {
    stage('Build') {
  
    }

    stage('Test') {
      when {
       expression {
         params.executeTests
       }
     }
        stage("Test1") {
          steps {
            echo 'teer'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
           steps {
            echo 'teer'
          }
        input(message: 'deploy?', ok: 'deploy')
        echo "deploy version ${params.VERSION}"
      }
    }

   

  }
}
