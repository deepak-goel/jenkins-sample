library 'flmu-reference-pipeline'

pipeline{

  agent any
  stages{
      stage('Init1'){
            steps{

              checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'githubclone', url: 'https://github.com/Layshah25/jenkins-stuff.git']]])

              sh 'ls'
              sh 'mkdir tm'
              dir('tm'){
              sh 'echo haha > t.txt'
              sh 'cat t.txt'
              stash includes: 't.txt', name: 't'
              }
        }
      }
      stage('Init2'){
          steps{
              sh 'hostname'
              
              sh 'ls'
              unstash 't'
              sh 'ls'
        }
      }
   }
}
