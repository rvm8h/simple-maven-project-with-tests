node ('master') {
     checkout scm
stage('Build') {
  withMaven(maven: 'Maven 3.3.3') {
      if (isUnix()) {
                     sh 'mvn -Dmaven.test.failure.ignore clean package'
                    }
      else {
               bat 'mvn -Dmaven.test.failure.ignore clean package'
          }
       }
   }
   stage('Results') {
    junit '**/target/surefire-reports/TEST-*.xml'
    archive 'target/*.jar'  
      }
}
