pipeline {
    agent any

    stages {
        stage('Print') {
            when{
                expression{
                    "${X-GitHub-Event}" == push
                }            
            }
            steps {
                echo "${Name}"
                echo "${message}"

                build job: '/pushDownstream'
            }
        }
    }
}
