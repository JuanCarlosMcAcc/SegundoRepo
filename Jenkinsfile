pipeline {
  agent any
  stages {
    stage('Fluffy Build') {
      steps {
        echo 'Placeholder'
        sh 'echo Edited Placeholder.'
      }
    }
    stage('Fluffy Test') {
      steps {
        sh 'sleep 5'
        sh 'echo Success!'
      }
    }
    stage('Fluffy Deploy') {
      steps {
        echo 'Placeholder'
        sh 'pwd'
        sh 'ls'
        sh 'echo "Prueba" > fichero.txt'
        echo '----------------------------'
        sh 'cat fichero.txt'
        sh 'ls'
        echo 'Fichero creado con exito'
        echo '_______Stage finalizado_______'
        echo "BUILD TRIGGER FUNCIONA CORRECTAMENTE___"
      }
    }
    stage('Network Check') {
      steps {
        sh 'ifconfig'
      }
    }

  }  
  
  post{
      always{
        emailext body: 'Test Message',
            subject: 'Test Subject',
            to: 'j.moratalla.campello@accenture.com'
      } 
      }
      success{
          echo "====++++success++++===="
      }
      failure{
          echo "====++++A execution failed++++===="
      }
}

