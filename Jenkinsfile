
pipeline{
  agent any
  stages{
    stage('Jenkins test 2'){
      steps {
        script{
          git checkout -b 'jenkins_branch_test'
          touch test
          git add .
          git commit -m 'test'
          git push origin jenkins_branch_test
          echo 'Working'
        } 
      }
    }
  }
}
