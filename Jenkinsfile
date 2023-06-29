pipeline{
    agent any

    stages{
        stage("Aws test credentials"){
            steps{
                withAWS(credentials: 'your-id-name', region: 'your-region'){
                    sh 'echo "Hello DevOps" > hello.txt'
                    s3Upload (acl: 'Private' , bucket: 'your-bucket-name' , file: 'hello.txt')
                    s3Download(file:'downloaded.txt', bucket:'your-bucket-name', path:'hello.txt',force:true) 
                    sh "cat downloaded.txt"

                }
            }
        }
    }
}
