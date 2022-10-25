pipeline {
    agent any

    stages {
        stage('Print') {
            steps {
                echo "${Name}"
                echo "${message}"

                build job: '/pushDownstream'
            }
        }
    }
}
