pipeline{ 

  agent any 

  tools{ 
    maven 'Maven' 
  } 

  stages{ 
    stage("Cleanup"){ 
      steps{ 
        sh "mvn --version" 
        sh "mvn compile" 
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
      }
    }
  } 

  post{ 
    always{ 
      echo "asdasdasfas" 
    } 

    success{ 
      echo "========pipeline executed successfully ========" 
    } 

    failure{ 
      echo "========pipeline execution failed========" 
    } 
  } 
} 
