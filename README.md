## Setup
### Web
```bash
  flutter run -d web-server --web-port=8080 --web-hostname=0.0.0.0
```  
### Mobile with remote adb
Check your mobile lan ip and feel free to use your own port configuration
```bash
  SMARTPHONE_LOCAL_IP = 192.168.0.10 (LAN IP)
  INTERNAL_PORT = 5555
```
### [Localhost command] Run the following command to switch adb on your device to work over the network using the internal port
```bash
  adb tcpip INTERNAL_PORT
```
### [Localhost command] Check adb connection from localhost
```bash
  adb connect SMARTPHONE_LOCAL_IP:INTERNAL_PORT
``` 
### [Localhost command] Starts ngrok tcp forwarding to your mobile or if you prefer you can forward a chosen port on your router to the mobile
Ngrok describes itself as “expose a local server behind a NAT or firewall to the internet.”, making our lives easier.
```bash
  ngrok tcp SMARTPHONE_LOCAL_IP:INTERNAL_PORT
```  
### [Gitpod command] Connect from your Gitpod to your localhost for debugging
```bash
  adb connect NGROK_ADDRESS:NGROK_PORT
  flutter run -d NGROK_ADDRESS:NGROK_PORT
```  
