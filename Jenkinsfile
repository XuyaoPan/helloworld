pipeline {
    parameters {
        string(name:"Owner", defaultValue: "Nina", description: "owner of the job")
        choice(name: "Team", choices: ["kinsha", "rhea", "atlas"], description: "team of the owner")
    }
    agent any
    stages {
        stage("check out"){
            steps {
                git 'git@github.com:XuyaoPan/helloworld.git'
            }

        }
        stage("build step") {
            steps {
                echo "this is the build step"
            }
        }
        stage("test step") {
            steps {
                echo "this is the test step"
                echo "tested by $params.Owner from $params.Team team"
                sh 'python3 helloworld.py Tom'
            }
        }
    }
    post {
        success {
            echo "the build is successed"
        }
        failure {
            echo "the build is failed"
        }
    }
}