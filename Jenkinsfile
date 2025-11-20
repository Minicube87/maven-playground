pipeline{ 

  agent any 

  tools{ 
    maven 'Maven' 
  } 

  stages{ 

    stage("Cleanup"){ 
      steps{ 
        sh "mvn --version" 
        sh "rm -rf ./*"

      }       
    } 

    stage('Checkout') {
      steps { 
        checkout scm 
      }
    }

    stage("Compile"){
      steps{
        sh "mvn compile"
      }
    }

    stage("Test"){
      steps{
        sh "mvn test"
      }
    }

    stage("Package"){
      steps{
        sh "mvn package"
        sh "ls -R target"
      }
    }

    stage("Install"){
      steps{
        sh "mvn install"
      }
    }

    stage("Dependencies"){
      steps{
        sh "mvn dependency:tree"
      }
    }
    

  } 

  post{ 
    always{ 
      //sh "mvn clean"
      echo "dsadasdasdsadsads" 
    } 

    success{ 
      echo "========pipeline executed successfully ========" 
    } 

    failure{ 
      echo "========pipeline execution failed========" 
    } 
  } 
} 
