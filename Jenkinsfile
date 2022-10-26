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
            when{
                expression{
                    "$x_github_event" == "pull_request"
                }            
            }
            steps {
                echo "${PRtitle}"

                build job: '/prDownstream'
            }
        }
        stage('Issue comment'){
            when{
                expression{
                    "$x_github_event" == "issue_comment"
                }
            }
            steps{
                echo "${Comment}"

                script{
                    def text = toString(${Comment})
                    if(text =~ /!test/) {
                        echo "Radiii"
                        build job: '/issuecommentDownstream'
                    }    
                }
                
            }
        }
    }
}
