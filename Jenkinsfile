node {
    
    stage('Git clone'){
        git 'https://github.com/muzafferjoya/Node-Test.git'
    }
    
    stage('Upload') {

        dir('/var/lib/jenkins/workspace/pipe1'){

            pwd(); 

                 withAWS(region:'us-east-1',credentials:'8bcb1ea0-1619-4648-8d65-b57108eba01e') {

                 def identity=awsIdentity();
		def accounts = listAWSAccounts()

                 s3Upload(bucket:"eroam-front", workingDir:'.', includePathPattern:'**/*');
            }

        };
    }
}
