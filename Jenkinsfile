node {
    
    stage('Git clone'){
        git 'https://github.com/muzafferjoya/Node-Test.git'
    }
    
    stage('Upload') {

        dir('/var/lib/jenkins/workspace/job4'){

            pwd(); 

                 withAWS(region:'us-east-1',credentials:'397ec9da-8e18-46f3-a261-93d5dbf2e821') {

                 def identity=awsIdentity();

                 s3Upload(bucket:"eroam-frontend", workingDir:'.', includePathPattern:'**/*');
            }

        };
    }
}
