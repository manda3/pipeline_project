pipeline {
      agent any
         stages {
            stage('one') {
                   steps {
                         echo 'hi, this is jenkin job list'
                         }
                         {
            stage('two') {
                    steps {
                          input('do u want to proceed')
                          }
                          }
            stage('three'){
                    steps {
                          when {
                                not {
                                     branch "master"
                                     }
                                }
                           steps {
                                   echo "hello"
                                 }
                            }
              stage('four') {
                       steps {
                           parallel {
                              stage('unit test') {
                                           steps  {
                                                echo "running the unit test"
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
