pipeline {
    agent any
    tools {
        maven "m3"
    }
    stages {
      stage("checkout"){
        steps {                
            git branch: "main", url: "https://github.com/campanula/lbg-hello-world-maven.git"
            }
        }
        stage("build"){
            steps {
                echo "build"
            }
        }
           stage("deploy"){
               steps{
                   sh "mvn clean compile"
               }
           }
            stage("test"){
                steps{
                     sh "mvn test"
                }
            }
            stage("package"){
                steps{
                     sh "mvn -Dmaven.test.skip -Dmaven.compile.skip package"
                }
            }
        }
    }
