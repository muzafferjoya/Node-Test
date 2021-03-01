node {
    
    stage('Git clone'){
        git 'https://github.com/muzafferjoya/Node-Test.git'
    }
    
    stage('AWS Credentials Check') {

        dir('/var/lib/jenkins/workspace/pipe1'){

            pwd(); 

                 withAWS(region:'us-east-1',credentials:'aws-id') {

                 def identity=awsIdentity();
		

                 
            }

        };
    }
}
