pipeline {
    agent any

    stages {
        stage('Print') {
            when{
                expression{
                    "$X_GitHub_Event" == "push"
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
