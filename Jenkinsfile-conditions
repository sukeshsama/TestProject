pipeline {
    agent any
    stages {
        stage('Example') {
            steps { 
                echo 'Hello World'
            }
        }
        stage('Example2') {
            when {
                 // Only say hello if a "greeting" is requested
                expression { params.APP.contains('c2') }
            }
            steps {
                echo 'Hello c2'
            }
        }
        stage ('Example 3') {
            steps {
                script {
                    if (params.APP.contains('c1')) {
                        echo 'Hello c1'
                        sh "echo $APP | sed -r 's/[1]+/2/g'"
                    } else {
                        echo 'No c1'
                        sh "echo no C1 $APP"
                        
                    }
                }
            }
        }
    }
}
