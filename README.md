# HackTheBox-InviteCode

Hack The Box (https://www.hackthebox.eu/) requires you to generate an Invite Code in order to SignUp first. You should first try to generate the Invite Code by the hints given on their website. I used following command/script to generate the Invite code which may help you (But I discourage you to use it. Hack it at your own first).

## Linux Command
```
$ curl -X  POST -s  https://www.hackthebox.eu/api/invite/generate/ | cut -d : -f 4 | cut -d , -f 1 |  sed 's/"//g' |  base64 -d
```

## Python Script
```
#!/usr/bin/python
import requests
from requests.exceptions import HTTPError
import base64

response = requests.post('https://www.hackthebox.eu/api/invite/generate/',headers={'User-Agent': 'Mozilla 5'})
jsonResponse = response.json()
print("Use following Invite Token")
print(base64.decodestring(jsonResponse["data"]["code"]))
```
