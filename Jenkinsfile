pipeline { 
    agent {
            label 'LINUX'
        } 
    stages {
        stage('Build') { 
            steps { 
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Test'){
            steps {
                sh  'mvn test' 
            }
			post {
               always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        
    }
}
