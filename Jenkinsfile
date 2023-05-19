pipeline {
    agent any
    triggers{ pollSCM('*/1 * * * *') }
    
    stages {
        stage('Build') {
            steps {
                script{
                    build()
                }
            }
        }
        stage('Install pip deps') {
            steps {
                script{
                    deps()
                }
            }
        }
        stage('Deploy to DEV') {
            steps {
                script{
                    deploy("DEV") //, 1010)
                }
            }
        }
        // stage('Tests on DEV') {
        //     steps {
        //         script{
        //             test( "DEV")
        //         }
        //     }
        // }
        // stage('Deploy to STG') {
        //     steps {
        //         script{
        //             deploy("STG") //, 2020)
        //         }
        //     }
        // }
        // stage('Tests on STG') {
        //     steps {
        //         script{
        //             test("STG")
        //         }
        //     }
        // }
        // stage('Deploy to PRD') {
        //     steps {
        //         script{
        //             deploy("PRD") //, 3030)
        //         }
        //     }
        // }
        // stage('Tests on PRD') {
        //     steps {
        //         script{
        //             test("PRD")
        //         }
        //     }
        // }
    }
}

// for windows: bat "npm.."
// for linux/macos: sh "npm .."

def build(){
    echo "Building of node application is starting.."
}

def deps(){
    echo "Installing all required dependencies"
    bat "npm install"
    bat "npm install -g pm2"
    //bat "npm test"
}

def deploy(String environment){ //def deploy(String environment, int port){ 
    echo "Deployment to ${environment} has started.."
    //bat "pm2 delete \"Jenkins-${environment}\""
    //bat "pm2 start -n \"Jenkins-${environment}\" index.js -- ${port}"
}

//def test(String test_set, String environment){
    //echo "Testing test set on ${environment} has started.." //"Testing ${test_set} test set on ${environment} has started.."
    //bat "npm run ${test_set} ${test_set}_${environment}"
//}