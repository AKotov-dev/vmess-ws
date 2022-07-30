# vmess-ws - personal security server
+ Install the `vmess-ws` package (rpm/deb) on your foreign VPS. The server will be started immediately on port 8083. No additional actions are required.
+ Install the client [XRayGUI](https://github.com/AKotov-dev/XRayGUI) or [Qv2Ray](https://github.com/AKotov-dev/Qv2Ray_XRay_Installer) to your computer.
+ Copy the script shown below to the clipboard. Insert it into the terminal, specify the name or IP of your VPS instead of `192.168.0.100` and press `Enter`.
```
clear; VPS='192.168.0.100'; CONFIG=$(echo "{\"v\":\"2\",\"ps\":\"my-vps\",\"add\":\"$VPS\",\"port\":\"8083\",\"id\":\"e274f0d2-0f5f-11ed-99de-8ba9dddec48c\",\"aid\":\"0\",\"net\":\"ws\",\"scy\":\"auto\",\"sni\":\"\",\"type\":\"\",\"host\":\"example.com\",\"path\":\"/vmess\",\"tls\":\"\"}" | base64 | tr -d [:space:]); echo "vmess://$CONFIG"
```
+ Copy the received URL (vmess://...) to the clipboard, paste it into XRayGUI (button `Paste`) and press the `Start` button.
+ Set up a proxy connection in your browser SOCKS5 127.0.0.1:client_port. DNS redirect to it (enable the appropriate check box). You can already get to work. Your new location can be checked here: https://whoer.net

**Note:** The time on the client and server must be synchronized. The time zone does not matter.  Tested in Mageia-8, Fedora-36 and LUbuntu-22.04. Don't forget to open port 8083 on the server and client. Similar project - [SS-Obfuscator](https://github.com/AKotov-dev/SS-Obfuscator).
