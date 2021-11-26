pipeline {
    agent any # or agent { label: "linux" } # or agent { label: "windows" } or agent { label: "mac" }  or agent { label: "windows-2008" }

    stages {
        stage('Build the website') {
            steps { # they can be anything but usually a shell script
                sh "./ci-scripts/build.sh"
            }
        }

# usually we add a unit test here 

        stage ('Deploy the website') {
            steps {
                sh "./ci-scripts/deploy.sh"
            }
        }
    }
}