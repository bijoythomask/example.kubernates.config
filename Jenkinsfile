pipeline {
  agent any

  parameters {
        stringParam(defaultValue: true, description: 'Build number of build image build', name: 'IMAGE_BUILD_NUMBER')
  }


  stages {
    stage('Deploy front-end') {
      agent any
      steps {
        sh 'echo  \'Hello Kubernates world\''

        kubernetesDeploy(
          configs: 'front-end/front-end.deployment.yaml',        
          enableConfigSubstitution: true,          
          kubeconfigId: 'ubuntu-virtual-machine'          
        )
      }
    }
  }
}