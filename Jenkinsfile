pipeline {
    agent any

    stages {
        stage('Push') {
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
        stage('PR'){
            echo "blabla"
        }
    }
}
