pipeline {
  agent any
  stages {
    stage('Openshift Build') {
      steps {
        openshiftBuild(bldCfg: 'openshift-sample-webapp', namespace: 'project-dev', waitTime: '600000')
      }
    }
  }
}