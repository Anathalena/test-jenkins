pipeline {
    agent any

    stages {
        stage('Print') {
            when{
                expression{
                    "$x_github_event" == "push"
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
