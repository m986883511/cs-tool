pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'python setup.py build'
            }
        }
        stage('Test'){
            steps{
                echo 'Testing the app'
            }
        }
        stage('msg'){
            steps{
                wxwork(
                    robot: 'jenkins',
                    type: 'text',
                    text: [
                        '${JOB_NAME}-${BRANCH_NAME}-${BUILD_NUMBER}构建成功'
                    ]
                )
            }
        }
    }
}