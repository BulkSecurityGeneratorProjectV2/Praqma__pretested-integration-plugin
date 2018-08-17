
def pattern = 'MultiBranchPipePreSCM'

def triggerBranchPattern = '*/ready' + pattern + '/*'
def integrationBranch = 'master' + pattern


node {
  stage ('Checkout'){
    checkout scm
/**
    checkout([
      $class: 'GitSCM',
      branches: [[name: triggerBranchPattern ]],
      userRemoteConfigs: [[
        name: 'origin',
        url: 'git@github.com:bicschneider/test-git-phlow-plugin.git'
      ]],
      extensions: [
        pretestedIntegration(
          gitIntegrationStrategy: accumulated(),
          integrationBranch: integrationBranch,
          repoName: 'origin')
        ,
        [ $class: 'ChangelogToBranch',
          options: [compareRemote: 'origin', compareTarget: integrationBranch]
        ],
        [$class: 'PruneStaleBranch']
      ]
    ])
    */
//    try {
//      sh '''
//      if [ -e ./build_failed.md ]; then
//        exit 1
//      fi
//      '''
//    } catch(Exception e) {
//      currentBuild.result = 'UNSTABLE'
//    }
    pretestedIntegrationPublisher()
  }
}
