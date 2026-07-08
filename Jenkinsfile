pipeline{
    agent any
    stages {
        stage ('build'){
            steps{
                sh 'mv clean package'
            }
        }
    }
    post{
        success{
            echo 'build successful'
        }
        failure
            echo 'build failed'
        }
    }
}