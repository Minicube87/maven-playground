pipeline{ 

  agent any 

  tools{ 
    maven 'Maven' 
  }

  parameters {
    choice(name: 'PROFILE', choices: ['dev', 'prod'], description: 'Maven-Profil')
    choice(name: 'SKIP_TESTS', choices: ['true', 'false'], description: 'Tests überspringen?')
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

    stage('Build') {
      steps {
        sh "mvn clean package -P${params.PROFILE} -DskipTests=${params.SKIP_TESTS}"
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
