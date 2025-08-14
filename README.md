# simpleWebAppDeploy
This repo is used to perform basic actions of git and deploying application using AWS code pipeline
Basic Html application is inside the index.html which will replace the existing file on the actual server(EC2) location /var/www/html/index.html
AWSTask5snapshot.docx has snapshots of code pipeline pushed, EC2 instance, and actual application running on public IP
buildspec file will pick up all the files in the source and make it available for buildartif.zip in the folder defined in code build like deploy
appspec.yml will pick up the artifacts from the folder codepipeline-586567587-65765874686/deploy/* and will deploy the application from the artifacts to /var/www/html/

Note* if there is a file already present in /var/www/html/ it will be overwrite by codePiepeline only if it that file has required permission set to replace else you will end up in an error by codePipeline as unhealthy instance constaraint exception

Note2* to update your application you just need to commit on github and it will release new version of application Also, you have to keep all relatable files of application like html, css etc at same level of structure so that they will be deployed in /var/www/html/*
