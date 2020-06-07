pipeline {
    agent any
    stages {
        stage("Build"){
            steps{
            echo "Working as expected"
            echo "This Should Trigger Build"
            }
        }        
    }
    post { 
        success { 
            echo 'I will always say Hello again!'
            sh '''
            curl "https://api.GitHub.com/repos/<GitHubUserName>/<REPO_NAME>/statuses/$GIT_COMMIT?access_token=afe9e5ea0e00ebafcdeff6b37b322476c0bf676c" \
  -H "Content-Type: application/json" \
  -X POST \
  -d "{\"state\": \"success\",\"context\": \"continuous-integration/jenkins\", \"description\": \"Jenkins\", \"target_url\": \"http://ec2-52-90-63-31.compute-1.amazonaws.com:8080/job/Learning/job/pipeline-webhook-git/$BUILD_NUMBER/console\"}"
'''
        }
    }
}
