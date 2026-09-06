pipeline {
    parameters {
        string(name:"Owner", defaultValue: "Nina", description: "owner of the job")
        choice(name: "Team", choices: ["kinsha", "rhea", "atlas"], description: "team of the owner")
    }
    agent any
    stages {
        stage("build step") {
            steps {
                echo "this is the build step"
            }
        }
        stage("test step") {
            steps {
                echo "this is the test step"
                sh 'python3 hello_world.py $params.Owner $params.Team'
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
