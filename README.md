# How To Install uTorrent Web UI for Ubuntu series
The latest version of uTorrent for Linux was released for Ubuntu 13.04, but we can still run it in Ubuntu 18.04 LTS and Latest. Go to uTorrent Linux download page to download the uTorrent server package for Ubuntu 13.04.

1. Alternatively, you can open up a terminal window and run the following command to download it from the command line.
   
   64 Bit
   ```
   wget http://download.ap.bittorrent.com/track/beta/endpoint/utserver/os/linux-x64-ubuntu-13-04 -O utserver.tar.gz
   ```
   32 Bit
   ```
   wget http://download.ap.bittorrent.com/track/beta/endpoint/utserver/os/linux-x64-ubuntu-13-04 -O utserver.tar.gz
   ```
2. Once downloaded, change working directory to the directory where uTorrent server file is downloaded. Then run the following command to extract the tar.gz file to /opt/ directory.
   ```
   sudo tar xvf utserver.tar.gz -C /opt/
   ```
3. Next, install required dependencies by executing the following command
   ```
   sudo apt install libssl1.0.0 libssl-dev
   ```
   Note that if you are using Ubuntu 19.04 and Latest, you need to download the libssl1.0.0 deb package from Ubuntu 18.04 repository and install it, because libssl1.0.0 isn’t included in Ubuntu Latest software repository.
   ```
   wget https://launchpad.net/ubuntu/+archive/primary/+files/libssl1.0.0_1.0.2n-1ubuntu5_amd64.deb
   ```
   ```
   sudo apt install ./libssl1.0.0_1.0.2n-1ubuntu5_amd64.deb
   ```
4. After the dependencies are installed, create a symbolic link.
   ```
   sudo ln -s /opt/utorrent-server-alpha-v3_3/utserver /usr/bin/utserver
   ```
5. Use the following command to start uTorrent server. By default, uTorrent server listens on 0.0.0.0:8080. If there’s another service also listens on port 8080, you should temporarily stop that service. uTorrent will also use port 10000 and 6881. The -daemon option will make uTorrent server run in the background.
   ```
   utserver -settingspath /opt/utorrent-server-alpha-v3_3/ -daemon
   ```
6. You can now visit the uTorrent web UI in your browser by typing in the following text in the web browser address bar.
   ```
   "your-server-ip":8080/gui
   ```
   If you are installing uTorrent on your local computer, then replace your-server-ip with localhost.
   ```
   localhost:8080/gui
   ```
7. If there’s a firewall on your Ubuntu server, then you need to allow access to port 8080 and 6881. For example, if you are using UFW, then run the following two commands to open port 8080 and 6881.
   ```
   sudo ufw allow 8080/tcp
   ```
   ```
   sudo ufw allow 6881/tcp
   ```
8. Please note that /gui is needed in the URL, otherwise you will encounter invalid request error. When asked for username and password, enter admin in username field and leave password filed empty.
   ```
   admin
   ```
# Now u can using the uTorrent
![image](https://github.com/bimacakra30/Torrent/assets/160693155/97ede315-b723-4111-8600-c404ef270775)
