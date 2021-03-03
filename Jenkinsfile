node {
    
    stage('Git clone'){
        git 'https://github.com/muzafferjoya/Node-Test.git'
    }

    stage('Install Dependencies'){
	sh 'npm install'
}

    stage('Node Test'){
	sh 'npm run test'
}

    
    stage('AWS Credentials Check') {

        dir('/var/lib/jenkins/workspace/pipe1'){

            pwd(); 

                 withAWS(region:'us-east-1',credentials:'aws-id') {

                 def identity=awsIdentity();
		
		s3Upload(bucket: "muzaffar-khan", workingDir: '.', includePathPattern:'**/*', excludePathPattern:'node_modules/*');
                 
            }

        };

	}
    }

