取得 root 密碼
docker exec -it gitlab-ce grep 'Password:' /etc/gitlab/initial_root_password


test

(ok)new account

(ok)clone https
http://172.25.91.66:81/

(ok)clone ssh  
git clone ssh://git@172.25.91.66/eueip/test.git

(ok) push 

-----------------
modify remote https url
git remote set-url origin http://172.25.91.66:81/eueip/test.git
ssh url
git remote set-url origin ssh://git@172.25.91.66/eueip/test.git

vm
git clone ssh://git@10.0.2.15:22/eueip/test.git
