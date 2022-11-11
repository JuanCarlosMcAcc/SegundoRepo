@Library('libreria-jc@main') _
pipeline {
        agent any
        environment{
            NOMBRE = 'Juan Carlos'
            MI_CARPETA = 'CarpetaJC'
            VERSION = 'INT'
            CONTADOR = 12
        }
        stages {
            stage('verify') {
                steps {
                    HelloWorldSimple('HOLA SOY EL PARAMETRO')
                    HelloWorldSimple('JuanCarlos', 'Moratalla', 'Campello')
                    HelloWorldSimple(1)
                    echo "-------------------------------"
                    echo "Numero de build --->  $env.BUILD_NUMBER"
                    echo "-------------------------------"
                    helloWorld(name: "Juan Carlos", dayOfWeek: "Viernes")
                    sh "pwd"
                    sh "ls"
                    sh "cat hello_world.txt"
                    sh "pwd"
                }
            }
            stage('Read File') {
                steps {
                    sh "cat release.yml"
                    echo """--
                    --
                    --
                    --"""
                    echo "La version utilizada es : "
                    sh ("grep ${VERSION} release.yml")
                }
            }
            stage('Read File Libreria') {   
                steps { 
                    echo "Llamada librería..."
                    
                    // switchCaseVersion(inputEnv())
                }
            }
            stage('Ejercicio 2'){
                steps{
                    script{
                        def archivo = readYaml(file:'release.yml')
                        println archivo.getClass().getName()
                        sh "cat release.yml"
                        List<String> keys = new ArrayList<>(archivo.keySet());
                        List<String> values = new ArrayList<>(archivo.values());
                        println "-----"
                        print " Las version es -> " + values[2]
                        println "-----"
                        for (int i = 0; i < values.size(); i++){
                            println "La version de " + keys[i] +" es "+ values[i]
                        }
                    }
                }
            }
            stage('Ejercicio 3'){
                steps{
                    script{
                        def archivo = readYaml(file:'release.yml')
                        List<String> keys = new ArrayList<>(archivo.keySet());
                        List<String> values = new ArrayList<>(archivo.values());
                        print values
                        print archivo
                        
                        sh "rm release.yml"

                        archivo.put("APP_JAVA-INT","1.1.0")
                        print archivo
                        writeYaml file: 'release.yml', data :  archivo
                        
                        sh "cat release.yml"

                        // for (int i = 0; i < values.size(); i++){
                        //     // println "La version de " + keys[i] +" es "+ values[i]
                        //     writeYaml file: 'release1.yml', data :  values[i]
                        // }
                        // sh "cat release1.yml"

                        // File file = new File("release.yml")
                        // FileOutputStream fos=new FileOutputStream(file);
                        // ObjectOutputStream oos=new ObjectOutputStream(fos);

                        // oos.write("Hola :")
                        // oos.flush();
                        // fos.close();
                        // sh "cat release.yml"
                    }
                }
            }
            stage("Pruebas Script"){
                steps{
                    sh "ls"
                    sh "bash script1.sh ${CONTADOR}"
                }
            }
        }
    }








// Esto es para el pipeline sin librerias

// pipeline {
//   agent any
//   stages {
//     stage('Fluffy Build') {
//       steps {
//         echo 'Placeholder'
//         sh 'echo Edited Placeholder.'
//         echo "====++++  El valor de la variable es ${NOMBRE}  ++++===="
//       }
//     }
//     stage('Fluffy Test') {
//       steps {
//         sh 'sleep 5'
//         sh 'echo Success!'
//       }
//     }
//     stage('Fluffy Deploy') {
//       steps {
//         echo 'Placeholder'
//         sh 'pwd'
//         sh 'ls'
//         sh 'echo "Prueba" > fichero.txt'
//         echo '----------------------------'
//         sh 'cat fichero.txt'
//         sh 'ls'
//         echo 'Fichero creado con exito'
//         echo '_______Stage finalizado_______'
//         echo "BUILD TRIGGER FUNCIONA CORRECTAMENTE___"
//       }
//     }
//     stage('Stage Paralelo') {
//       parallel {
//         stage('Backend') {
//           steps {
//             sh 'ls'
//             sh 'sleep 5'
//             sh 'pwd'
//             sh 'sleep 3'
//             echo '--------------------'
//             sh 'pwd'
//             sh 'sleep 5'
//             echo '--------------------'
//             sh 'mkdir ${MI_CARPETA}'
//             sh 'ls'
//           }
//         }
//         stage('Frontend') {
//           steps {
//             echo '--------------------'
//             echo 'Stage Frontend Paralelo'
//             echo 'La carpeta creada en el anterior Stage se llama ${MI_CARPETA}'
//             echo '--------------------'
//             echo '--------------------'
//           }
//         }
//         stage('Performance') {
//           steps {
//             echo '--------------------'
//             echo 'Stage Performance Paralelo'
//             echo '--------------------'
//           }
//         }
//         stage('Static') {
//           steps {
//             echo '--------------------'
//             echo 'Stage Static Paralelo'
//             echo '-------------------- '
//           }
//         }
//       }
//     }

//   }

//   environment{
//     NOMBRE = 'Juan Carlos'
//     MI_CARPETA = 'CarpetaJC'
//   }  
  
//   post{
//       always{
//         echo "====++++SIEMPRE SE EJECUTA ESA SECCION DEL POST++++===="
//         // emailext body: 'Test Message',
//         //     subject: 'Test Subject',
//         //     to: 'j.moratalla.campello@accenture.com'
//       } 
      
//       success{
//           echo "====++++success++++===="
//       }
//       failure{
//           echo "====++++A execution failed++++===="
//       }
//   }
// }

