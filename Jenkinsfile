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
        echo 'Stage finalizado'
        echo "BUILD TRIGGER FUNCIONA CORRECTAMENTE"
      }
    }
    stage("Stage de build remoto"){
        steps{
            echo "Prueba de cambio para trigger automatico hooks"
        }
        post{
            always{
                echo "====++++always++++===="
            }
            success{
                echo "====++++El commit se ha ejecutado y el trigger tambien++++===="
            }
            failure{
                echo "====++++A execution failed++++===="
            }
    
        }
    }
  }
}