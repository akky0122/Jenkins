pipeline
{
  agent any
  stages
  {
    stage('scm checkout')
    { steps { git branch: 'main', url: 'https://github.com/akky0122/Jenkins.git' }
     }

    stage('build the code')
    { steps { withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') 
      { sh 'mvn clean package' }  
    }}
     
  }
}
