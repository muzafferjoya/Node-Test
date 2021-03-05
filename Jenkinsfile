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

    
    stage('Upload to S3 Bucket') {

        dir('/var/lib/jenkins/workspace/node-test'){

            pwd(); 

                 withAWS(region:'us-east-1',credentials:'aws-id') {

                 def identity=awsIdentity();
		
		s3Upload(bucket: "muzaffar-react", workingDir: '.', includePathPattern:'**/*', excludePathPattern:'.git/*, **/node_modules/**');
                 
            }

        };

	}
    }

