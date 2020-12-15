pipeline{
  agent any
  stages{
    stage('Jenkins test auto'){
      steps {
        script{
          if(env.BRANCH_NAME == 'develop'){
            echo 'Currently on develop branch'
            echo env.git-cred
            echo git-cred
            sh 'pwd'
            sh 'ls'
            sh 'git checkout -b jenkins-generated-branch-retest'
            sh 'touch generatedfile'
            sh 'git add .'
            sh 'git commit -m "test generated file"'
            withCredentials([usernamePassword(credentialsId: 'git-cred', passwordVariable: 'git-pwd', usernameVariable: 'git-account')]) {
              sh('git push https://${git-account}:${git-password}@github.com/Ousmaneaba/tweets-search-app-2021.git')
            }
          }
        }
      }
    }
  }
}
