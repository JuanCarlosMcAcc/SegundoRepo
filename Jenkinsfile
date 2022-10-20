pipeline {
  agent any
  stages {
    stage('Fluffy Build') {
      steps {
        echo 'Placeholder'
        sh 'echo Edited Placeholder.'
        echo "====++++  El valor de la variable es ${NOMBRE}  ++++===="
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
    stage('Stage Paralelo') {
      parallel {
        stage('Backend') {
          steps {
            sh 'cd /home/jenkins/agent/workspace/Formacion/${NOMBRE}/pipeline-github'
            sh '--------------------'
            sh 'pwd'
            sh 'sleep 5'
            sh '--------------------'
            sh 'mkdir /home/jenkins/agent/workspace/Formacion/Juan Carlos/pipeline-github/${MI_CARPETA}'
            sh 'ls'
          }
        }
        stage('Frontend') {
          steps {
            sh './jenkins/test-frontend.sh'
            junit 'target/test-results/**/TEST*.xml'
          }
        }
        stage('Performance') {
          steps {
            sh './jenkins/test-performance.sh'
          }
        }
        stage('Static') {
          steps {
            sh './jenkins/test-static.sh'
          }
        }
      }
    }

  }

  environment{
    NOMBRE = 'Juan Carlos'
    MI_CARPETA = 'CarpetaJC'
  }  
  
  post{
      always{
        echo "====++++SIEMPRE SE EJECUTA ESA SECCION DEL POST++++===="
        // emailext body: 'Test Message',
        //     subject: 'Test Subject',
        //     to: 'j.moratalla.campello@accenture.com'
      } 
      
      success{
          echo "====++++success++++===="
      }
      failure{
          echo "====++++A execution failed++++===="
      }
  }
}

