pipeline {
  agent any

  parameters {
        string(defaultValue: "1", description: 'Build number of build image build', name: 'IMAGE_BUILD_NUMBER')
        choice(choices: ['US-EAST-1', 'US-WEST-2'], description: 'What AWS region?', name: 'region')
  }


  stages {
    stage('Deploy front-end') {
      agent any
      steps {

        sh 'echo  \'Deploying kubernetes front-end artifacts.\''
               
        kubernetesDeploy(
          configs: 'front-end/front-end.deployment.yaml,front-end/front-end.service.yaml,ingress.yaml',        
          enableConfigSubstitution: true,          
          kubeconfigId: 'ubuntu-virtual-machine'          
        )
      }
    }
  }
}