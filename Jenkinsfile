pipeline {
  agent any
  stages {
    stage('Openshift Build') {
      steps {
        openshiftBuild(bldCfg: 'openshift-sample-webapp', namespace: 'project-dev', waitTime: '600000')
      }
    }
    stage('Start XLR Release') {
      steps{
        xlrCreateRelease serverCredentials: 'admin', template: 'Samples/Motor tributario Release', releaseTitle: 'Release for $BUILD_TAG', variables: [[propertyName: 'VERSION', propertyValue: '$BUILD_NUMBER.0'], [propertyName: 'SERVICE_NOW_SYSID', propertyValue: 'dummy']], startRelease: true
      }
    }
  }
}