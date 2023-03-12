pipeline
{
  agent any
  stages
  {
    stage('scm checkout')
    { steps { git branch: 'main', url: 'https://github.com/m1m2m3/DevOps-Batch.git' } }

    stage('build the code')
    {  steps { withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME')
      { sh 'mvn clean package' }  
             }}
   
     stage ('deploy to dev') {
             steps {
                  sshagent(['user-deployer']) {
                  sh "scp -o StrictHostKeyChecking=no */target/*.war ec2-user@3.111.40.171:8080/:/usr/local/tomcat/webapps/"
} } }

  }
}
