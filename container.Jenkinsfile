pipeline {

    agent {
        dockerfile {

            filename 'Dockerfile'
            //args '-u 0'

        }
    }

    stages {

        stage ('echo'){

            steps {

                sh 'whoami'
                sh 'pwd'

                ansiColor('xterm') {

                    ansiblePlaybook( 

                        playbook: './playbook.yaml',
                        inventory: './hosts', 
                        credentialsId: 'sample-ssh-key',
                        colorized: true

                    ) 

                }

            }

        }

    }    

}