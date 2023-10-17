# How to use
```
$ git clone https://tea.connectivity.tw/ConnLab_5G_Sec/o-du-l2_basic
$ cd o-du-l2_basic
```
# 建立架構
# 1. 必要條件
## 安裝 docker & compose
```
$ curl -fsSL https://get.docker.com -o - | bash
```
ref. https://docs.docker.com/engine/install/

# 建立架構
```
sudo docker compose up
```

# 進入 container 裡
#### o-du-l2-o1
```
sudo docker exec -it o-du-l2-o1_01 bash
```

# 開始實驗 odu with o1 (in container)

#### odu
```
cd /root/o-du-l2/bin/odu/
./odu
```

# 暫時離開 Docker compose (會保留資料)
```
在 sudo docker compose up 視窗按下 Ctrl + c 即可
下次要開再下 sudo docker compose up
```

# Troubleshooting
# 看看 netopeer2-server 有沒有啟動 (in container)
```
ps aux | grep -v grep | grep netopeer2-server
```

# 其他
#### tmux 使用
C-b 指的是 Ctrl + b 同時按  
新增分頁：C-b c  
切換分頁：C-b 數字  
離開tmux：C-b d  

# 危險指令
# 請先確定都了解指令再使用

#### (請確定要這麼做，再下這個指令) 不保留資料，並重新編譯架構 (rebuild)
`sudo docker compose up --build`

#### (請確定要這麼做，再下這個指令) 不保留資料，並移除架構
`sudo docker compose down`

####  (請確定要這麼做，再下這個指令) Reset Docker Setting
`sudo docker system prune`

####  (請確定要這麼做，再下這個指令) Delete all containers 
`sudo docker rm -f $(sudo docker ps -a -q)`

####  (請確定要這麼做，再下這個指令) Delete all images 
`sudo docker rmi -f $(sudo docker images -a -q)`