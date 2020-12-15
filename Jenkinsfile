pipeline{
  agent any
  stages{
    stage('Jenkins test auto'){
      steps {
        sh 'pwd'
        sh 'ls'
        sh 'git checkout -b jenkins-generated-branch'
        sh 'touch generatedfile'
        sh 'git add .'
        sh 'git commit -m "test generated file"'
        sh 'git push origin jenkins-generated-branch'
        script{
          echo 'Working'
        }
      }
    }
  }
}
