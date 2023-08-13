pipeline {

  agent any

  parameters {
    choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description:'')
    booleanParam(name: 'executeTests', defaultValue: true, description:'')
  }
  stages {
    stage("Build") {
      steps {
        echo 'nafnna'
      }
    }

    stage("Test") {
      when {
       expression {
         params.executeTests
      }
        }  
          steps {
            echo 'nafna'
          }
    }

    stage("Deploy") {
      steps {
          script{
               def dockerCmd = 'docker run -p 3080:3080 -d nanajanashia/demo-app:1.0'
               sshagent(['ec2-server-key']) {
                    sh "ssh -o StrictHostKeyChecking=no ec2-user@16.171.10.109 ${dockerCmd}"  
               }
          }
      }
    }

  }
}
