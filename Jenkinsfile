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
//        cat 'Esto es una prueba para almacenar en el fichero' > fichero1.txt
        sh 'ls'
        sh 'echo "Prueba" > fichero.txt'
        sh 'cat ficherto.txt'
        echo 'Prueba stage Fluffy finalizado'
        echo 'Stage finalizado'
      }
    }
    stage("Stage de build remoto"){
        steps{
            echo "Prueba de cambio para trigger automatico"
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