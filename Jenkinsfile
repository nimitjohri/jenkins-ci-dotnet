pipeline {
agent any

environment {
   PATH = "C:\\Windows\\System32"
}

stages {
stage ('Checkout') {
            git 'https://github.com/nimitjohri/jenkins-ci-dotnet.git' 
            }
}
stage ('Restore Packages') {     
         steps {
             bat '"C:\\Program Files\\dotnet\\dotnet.exe" restore "D:\\Dev Ops Training\\jenkins-ci-dotnet\\src\\MyWindowsService\\MyWindowsService.sln" ' 
          }
        }
// stage('Clean') {
//       steps {
//             bat '"C:\\Program Files\\dotnet\\dotnet.exe" clean'
//        }
//     }
stage('Build') {
     steps {
            bat "\"${tool 'MSBuild'}\" D:\\DevOps Training\\DemoPipeline\\jenkins-ci-dotnet\\src\\MyWindowsService\\MyWindowsService.sln /p:Configuration=Debug /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
      }
   }
 }
}