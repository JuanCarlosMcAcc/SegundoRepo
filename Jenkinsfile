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
        echo "BUILD TRIGGER FUNCIONA CORRECTAMENTE"
      }
    }
  }  
  
  post{
      always{
          echo "====++++always++++====",
          subject: "Test Subject",
          body: "Test Message from Jenkins"          
          to: "jcmoratalla@devcenter.es"
      }
      success{
          echo "====++++success++++===="
      }
      failure{
          echo "====++++A execution failed++++===="
      }
  }
}
