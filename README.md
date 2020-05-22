# HackTheBox-InviteCode

Hack The Box (https://www.hackthebox.eu/) requires you to generate and Invite Code in order to SignUp first. You should first try to generate the Invite Code by the hints given on their website. I used following command to generate the Invite code which may help you (But I discourage you to use it).

$ curl -X  POST -s  https://www.hackthebox.eu/api/invite/generate/ | cut -d : -f 4 | cut -d , -f 1 |  sed 's/"//g' |  base64 -d

