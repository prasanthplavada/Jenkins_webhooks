pipeline {
    agent any
    environment {
        my_Name='Prasanth'
        artifact_passwd=credentials('artifact-secret')
    }
    parameters {
        booleanParam(name:'Boolean_Test',defaultValue:'true',description:'test boolean')
        
    }
    stages {
        stage('Predefined Variable') {
            steps {
                sh 'env | sort'
                echo "$BUILD_NUMBER"
            }
        }
        stage('Global Variable') {
            when {
               expression { params.booleanParam == 'true' }
            }
            steps {
                echo "$my_Name"
            }
        }
         stage('Stage Variable') {
             environment {
                my_No='223344' 
             }
            steps {
                echo "$my_Name" 
                echo "$my_No"
                echo "$artifact_passwd"
                              
            }
        }
        
    }
}
