pipeline {
  agent any
  stages {
    stage('Deploy front-end') {
      agent any
      steps {
        sh 'echo  \'Hello Kubernates world\''

        kubernetesDeploy(
          configs: 'front-end/front-end.deployment.yaml',        
          enableConfigSubstitution: true,
          kubeConfig: [path: ''],
          kubeconfigId: 'ubuntu-virtual-machine'
          secretName: ''
          ssh: [sshCredentialsId: '*', sshServer: '']
          textCredentials: [certificateAuthorityData: '', clientCertificateData: '', clientKeyData: '', serverUrl: 'https://']
        )
      }
    }
  }
}