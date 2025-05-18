pipeline{
    agent any
    stages{
        stage("One"){
            steps{
                echo "========executing One========"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }


        stage("Two"){
            steps{
                input("Do you want to proceed")
                echo "========executing Two========"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }

        stage("Three"){

            when {

                    not {

                        branch "master"
                    }

            }
            steps{
                echo "========executing Three========"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }

        stage("Four"){

            parallel{

                    stage("Unit test"){
                            steps{
                                    
                                    echo "========executing Unit test========"
                                }
                            post{
                                    always{
                                        echo "========always========"
                                    }
                                    success{
                                        echo "========A executed successfully========"
                                    }
                                    failure{
                                        echo "========A execution failed========"
                                    }
                                }
                            }


                    
                    stage("Integration test"){

                            agent {
                                    docker{
                                            reuseNode false
                                            image "ubuntu"
                                    }
                            
                            }
                            steps{
                                    
                                    echo "========executing Integration test========"
                                }
                            post{
                                    always{
                                        echo "========always========"
                                    }
                                    success{
                                        echo "========A executed successfully========"
                                    }
                                    failure{
                                        echo "========A execution failed========"
                                    }
                                }
                        }
                

            }

            
        }


    }
  
}