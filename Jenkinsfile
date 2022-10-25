pipeline {
    agent any

    stages {
        stage('Print') {
            when{
                expression{
                    params.X-GitHub-Event == push
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
