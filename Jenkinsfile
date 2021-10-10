pipeline {
   agent any
   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build'){
         steps{
            sh(script: 'docker images -a')
            sh(script: """ 
            sudo cd /home/azure-vote/
            sudo docker images -a
            sudo docker build -t jenkins-pipeline .
            docker images -a
            cd ..
            """)
         }
      }
    }
}
