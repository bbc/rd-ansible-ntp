@Library("rd-apmm-groovy-ci-library@v1.x") _

/*
 Uses Molecule to test this Ansible role
*/

pipeline {
    agent {
        label "ansible-test"
    }
    options {
        ansiColor('xterm') // Add support for coloured output
        buildDiscarder(logRotator(numToKeepStr: '10')) // Discard old builds
    }
    stages {
        stage('Linting') {
            steps {
                sh 'molecule lint'
                sh 'molecule syntax'
            }
        }
    }
    post {
        always {
            bbcSlackNotify()
        }
    }
}
