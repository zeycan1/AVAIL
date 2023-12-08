 #               AVAIL

 # Avail Light Node Kurulumu

# ![image](https://github.com/zeycan1/AVAIL/assets/108004368/6155727d-c9a1-4402-9d97-1c308672b795)

### Sistem Gereksinimleri
| Bileşenler | Minimum Gereksinimler | 
| ------------ | ------------ |
| ✔️CPU |	2+ vcpu|
| ✔️RAM	| 4+ GB |
| ✔️Storage	| 40+ GB SSD |
| ✔️UBUNTU | 22 |


### Sunucumuzu güncelleyelim
```
sudo apt update && sudo apt upgrade -y
sudo apt-get install make clang pkg-config libssl-dev build-essential
```
```
screen -S alight
```

### Avail Light Client'i yükleyelim
```
cd
wget https://github.com/availproject/avail-light/releases/download/v1.7.5-rc3/avail-light-linux-amd64.tar.gz
tar -xvzf avail-light-linux-amd64.tar.gz
mv avail-light-linux-amd64 avail-light
rm -rf avail-light-linux-amd64.tar.gz
```



### Servis dosyasını oluşturalım.
```
sudo tee /etc/systemd/system/availd.service > /dev/null <<EOF
[Unit]
Description=Avail Light Client
After=network.target
StartLimitIntervalSec=0
[Service]
User=root
ExecStart=/root/avail-light --network goldberg
Restart=always
RestartSec=120
[Install]
WantedBy=multi-user.target
EOF
```

### veeee Başlatalım
```
sudo systemctl daemon-reload
systemctl enable availd
sudo systemctl restart availd
```

### Loglar :)
```
journalctl -u availd -fo cat
```

![image](https://github.com/Core-Node-Team/Testnet-TR/assets/91562185/6c65bb10-3b46-4df8-a5b3-7cbf59e58cdc)



### Son blok görüntüleme
```
curl "http://localhost:7000/v1/latest_block"

```

##  Form doldurmayı unutmayın
* [Avail Light Node Form](https://docs.google.com/forms/d/e/1FAIpQLSeL6aXqz6vBbYEgD1cZKaQ4vwbN2o3Rxys-wKTuKySVR-oS8g/viewform)

## Linkler:
 * [Avail Resmi Websitesi](https://www.availproject.org/)
 * [Avail Resmi Twitter](https://twitter.com/AvailProject)
 * [Avail Resmi Discord](https://discord.gg/kkHAXZCNZa)
