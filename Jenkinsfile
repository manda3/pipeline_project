pipeline {
      agent any
         stages {
            stage('One') {
                   steps {
                         echo 'hi, this is jenkin job list'
                         }
                         }
            stage('Two') {
                    steps {
                          input('do u want to proceed')
                          }
                          }
            stage('Three'){
                    steps {
                          when {
                                not {
                                     branch "master"
                                     }
                                }
                           steps {
                                   echo "hello"
                                 }
                    } }
              stage('Four') {
                       steps {
                           parallel {
                              stage('unit test') {
                                           steps  {
                                                echo 'running the unit test'
                                                  }
                                                  }
                               stage('integration test') {
                                             agent {
                                                    docker {
                                                            reuseNode false
                                                            image 'ubuntu'
                                                            }
                                                    }
                                              steps {
                                                    echo 'running the integration testing'
                                                    }
                                                    }
                                       }
                                   }
                                   }
                           }
}
