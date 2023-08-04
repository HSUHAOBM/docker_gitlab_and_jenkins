進容器取密碼
cat /var/jenkins_home/secrets/initialAdminPassword
docker exec -it jenkins-jenkins-1 cat /var/jenkins_home/secrets/initialAdminPassword

權限設置
sudo chown -R 1000:1000 workspace/