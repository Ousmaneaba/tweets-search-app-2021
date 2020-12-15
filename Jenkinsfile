
pipeline{
  agent any
  stages{
    stage('Jenkins test 2'){
      steps {
        git(
          url: 'https://github.com/Ousmaneaba/tweets-search-app-2021.git',
          credentialsId: '9665bb49-1d4a-44e6-bad4-bf9cb12329b7',
        )
        script{
          ls
          echo 'Working'
        } 
      }
    }
  }
}
