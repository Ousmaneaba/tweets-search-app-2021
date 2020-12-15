pipeline{
  agent any
  stages{
    stage('Clean workspace'){
      steps {
        cleanWs()
      }
    }
    stage('Jenkins test auto'){
      steps {
        script{
          if(env.BRANCH_NAME == 'develop'){
            echo 'Currently on develop branch'
            sh 'pwd'
            sh 'ls'
            sh 'git checkout -b jenkins-generated-branch'
            sh 'touch generatedfile'
            sh 'git add .'
            sh 'git commit -m "test generated file"'
            sh 'git push origin jenkins-generated-branch'
          }
        }
      }
    }
  }
}
