pipeline{
  agent any
  environment {
    WAS_RELEASED = '0'
  }
  stages{
    stage('Create release branch'){
      steps {
        script{
          if(env.BRANCH_NAME == 'develop'){
            echo "Creating branch"
            sh "git checkout -b release_${env.BUILD_NUMBER}"
            withCredentials([usernamePassword(credentialsId: env.git_cred, passwordVariable: env.git_pwd, usernameVariable: env.git_account)]) {
              sh("git push https://${env.git_account}:${env.git_pwd}@github.com/Ousmaneaba/tweets-search-app-2021.git")
            }
            env.WAS_RELEASED = '1'
          }
          else{
            echo "Create release branch skipped"
          ) 
        }
      }
    }
    stage('Merge release branch into master'){
      steps {
        script{
          if(env.WAS_RELEASED == '1'){
            echo "Merging release branch into master"
            sh "git checkout -f master"
            withCredentials([usernamePassword(credentialsId: env.git_cred, passwordVariable: env.git_pwd, usernameVariable: env.git_account)]) {
              sh("git merge release_${env.BUILD_NUMBER}")
            }
          }
          else{
            echo "Merge release branch into master skipped"
          }
        }
      }
    }
  }
}
