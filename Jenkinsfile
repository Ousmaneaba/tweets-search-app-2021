pipeline{
  agent any
  stages{
    stage('Jenkins test auto'){
      steps {
        script{
          if(env.BRANCH_NAME == 'develop'){
            echo 'Currently on develop branch'
            echo env.git_cred
            echo git_cred
            sh 'pwd'
            sh 'ls'
            sh 'git checkout -b jenkins-generated-branch-reretest'
            sh 'touch generatedfile'
            sh 'git add .'
            sh 'git commit -m "test generated file"'
            withCredentials([usernamePassword(credentialsId: env.git_cred, passwordVariable: env.git_pwd, usernameVariable: env.git_account)]) {
              sh('git push https://Ousmaneaba:jenkinstest97@github.com/Ousmaneaba/tweets-search-app-2021.git')
            }
          }
        }
      }
    }
  }
}
