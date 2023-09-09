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

modify remote ssh url
git remote set-url origin ssh://git@172.25.91.66/eueip/test.git
git remote set-url origin git@172.25.202.38:eip/eueip_internal.git

vm
git clone ssh://git@10.0.2.15:22/eueip/test.git



-----------------------------------------------
RAM CPU 設置

vi /etc/gitlab/gitlab.rb
unicorn['worker_processes'] = 2

docker exec -it gitlab-ce gitlab-ctl reconfigure
docker exec -it gitlab-ce gitlab-ctl restart



------------------------------------

# 參考 docker => gitlab + runner
https://eandev.com/post/devops/gitlab-and-runner-on-same-host-using-docker/

------------------------------------



localhost dev 
0. git branch > dev 分支  : 切到 dev 開發
1. git push origin dev  : 推 dev 分支 (slack通知：上code、測試機部屬狀態)
2. 23 測試機測試:相關人員測試
3. 推回 main 分支
    確保本地與遠端倉庫 code 相同
        git checkout dev
        git pull origin dev --rebase
        git checkout main
        git pull origin main --rebase
    合併
        git merge dev
        git push origin main 
4. 36 正式機 , => 先維持手動丟檔案到36,大家習慣後設置36自動部屬


---------------------------------------------------------------