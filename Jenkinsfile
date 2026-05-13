@Library('Shared') _
pipeline{
    agent any
   # agent { label 'dev-server'}
    
    stages{
         stage ("code"){
         steps{
             sh "whoami"
             script{
                 git_clone("https://github.com/AshishRanjanMCA/django-notes-app.git", "main")
             }
         }   
        }
      stage ("Build"){
         steps{
             script{
                 docker_build("notes-app","latest","ashishranjanyadav")
             }
             }   
        }
        stage ("push to DockerHub"){
         steps{
            script{
                docker_push("notes-app","latest","ashishranjanyadav")
            } 
         }   
        }
       stage ("Deploy"){
         steps{
            script{
                docker_deploy()
            }
         }   
        }
        
    }
}
