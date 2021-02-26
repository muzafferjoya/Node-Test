node {
    
    stage('Git clone'){
        git 'https://github.com/muzafferjoya/Node-Test.git'
    }
    
    stage('Upload') {

        dir('/var/lib/jenkins/workspace/job4'){

            pwd(); 

                 withAWS(region:'us-east-1',credentials:'<aws_id>') {

                 def identity=awsIdentity();

                 s3Upload(bucket:"eroam-frontend", workingDir:'.', includePathPattern:'**/*');
            }

        };
    }
}
