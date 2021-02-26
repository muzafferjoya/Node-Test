node {
    
    stage('Git clone'){
        git 'https://github.com/muzafferjoya/Node-Test.git'
    }
    
    stage('Upload') {

        dir('/var/lib/jenkins/workspace/pipe2'){

            pwd(); 

                 withAWS(region:'us-east-1',credentials:'d6479d34-3a9c-4a43-b9ae-6ed9315db5f5') {

                 def identity=awsIdentity();

                 s3Upload(bucket:"eroam-frontend", workingDir:'.', includePathPattern:'**/*');
            }

        };
    }
}
