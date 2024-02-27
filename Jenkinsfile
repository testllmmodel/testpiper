

@Library(['piper-lib-os']) _
pipeline {
  agent any
  options {
    disableConcurrentBuilds()
  }

  environment {
    DEMOCREDS = 'SAPDEMOCRED'
    HOST = 'Https://testapp.com:8026'
    CLIENT = '120'
    REPO = 'testpiper'
    REPO_URL = " https://github.com/testllmmodel/testpiper.git"
  }

  stages {
    stage('gCTS Deploy') {
      when {
        anyOf {
          branch 'main'
        }
      }
      steps {
        gctsDeploy(
          script: this,
          host: HOST,
          client: CLIENT,
          abapCredentialsId: DEMOCREDS,
          repository: REPO,
          remoteRepositoryURL: REPO_URL,
          role: 'SOURCE',
          vSID: 'GIT')

      }
    }

}

}
