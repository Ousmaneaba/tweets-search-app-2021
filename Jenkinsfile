pipeline{
  agent any
  stages{
    stage('Jenkins test auto with branch name'){
      steps {
        script{
          if(env.BRANCH_NAME == 'develop'){
            echo "Currently on develop branch"
            sh "pwd"
            sh "ls"
            sh "git checkout -b release_${env.BUILD_NUMBER}"
            sh "touch generatedfile"
            sh "git add ."
            sh "git commit -m \"release ${env.BUILD_NUMBER}\""
            withCredentials([usernamePassword(credentialsId: env.git_cred, passwordVariable: env.git_pwd, usernameVariable: env.git_account)]) {
              sh("git push https://${env.git_account}:${env.git_pwd}@github.com/Ousmaneaba/tweets-search-app-2021.git")
            }
          }
        }
      }
    }
  }
}
