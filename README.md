# vmess-ws - personal security server
Install the `vmess-ws` package (rpm/deb) on your foreign VPS. The server will be started immediately on port 8083. No additional actions are required. Install the client [XRayGUI](https://github.com/AKotov-dev/XRayGUI) (preferably) or [Qv2Ray](https://github.com/AKotov-dev/Qv2Ray_XRay_Installer) to your computer.
+ Copy the script shown below to the clipboard and insert it into the terminal
```
clear; VPS='192.168.0.100'; CONFIG=$(echo "{\"v\":\"2\",\"ps\":\"my-vps\",\"add\":\"$VPS\",\"port\":\"8083\",\"id\":\"e274f0d2-0f5f-11ed-99de-8ba9dddec48c\",\"aid\":\"0\",\"net\":\"ws\",\"scy\":\"auto\",\"sni\":\"\",\"type\":\"\",\"host\":\"example.com\",\"path\":\"/vmess\",\"tls\":\"\"}" | base64 -w 0); echo "vmess://$CONFIG"
```
+ Specify the name or IP of your VPS instead of `192.168.0.100`
+ If necessary, сhange the id `e274f0d2-0f5f-11ed-99de-8ba9dddec48c`. A new id for the `client` (in this script) and in the server configuration file `/etc/vmess-ws/server.json` can be generated [here](https://www.uuidgenerator.net/)
+ If necessary, you can also change the port `8083` on the `client` (in this script) and in the `server` configuration file `/etc/vmess-ws/server.json`
+ Press `Enter`
+ Copy the received URL (vmess://...) to the clipboard, paste it into XRayGUI (button `Paste`) and press the `Start` button.
+ Set up a proxy connection in your browser SOCKS5 127.0.0.1:client_port. DNS redirect to it (enable the appropriate check box). Your new location can be checked [here](https://whoer.net)

**Note_1:** If the above is difficult for you, just use the graphics generator `vmess-ws-gen.tar.gz` (see the general list of repository files). Unzip the archive and run `vmes_ws_gen`. The interface is intuitive and does not need additional explanations. The resulting configurations have been tested and are already being used on real VPS.

![](https://raw.githubusercontent.com/AKotov-dev/vmess-ws/main/ScreenShot1.png)

**Note_2:** The time on the client and server must be synchronized. The time zone does not matter.  Tested in Mageia-8/9, Fedora-36 and LUbuntu-22.04. Don't forget to open port 8083 on the server and client.  
  
Similar project: [SS-Obfuscator](https://github.com/AKotov-dev/SS-Obfuscator)
