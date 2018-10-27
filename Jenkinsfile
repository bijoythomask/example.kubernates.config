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
        sh 'echo  \'Hello Kubernates world\''

        sh "echo ${params.region}"

        kubernetesDeploy(
          configs: 'front-end/front-end.deployment.yaml',        
          enableConfigSubstitution: true,          
          kubeconfigId: 'ubuntu-virtual-machine'          
        )
      }
    }
  }
}