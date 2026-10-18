# DESCRIPCIÓN:
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.

To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!

Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.cylabacademy.net/library/828ca80eed550dbc9645ad6c2aa5c2061b2dd2e8e4098b1c7fe6d639459ea5a5/myNetworkTraffic.pcap) and try to get the flag.

Filter your packets to narrow down your search.

Attacks were done in timely manner.

Time is essential
# SOLUCIÓN:
#### academy{1t_w4snt_th4t_34sy_tbh_4r_6b09861f}
```
┌──(mony㉿Mony)-[~/forensic]
└─$ strings myNetworkTraffic.pcap
lqNaBwM=Tq
WOY4pqw=Tq
YWNhZGVteQ==Tq
PxgfcUc=Tq
mvKwnFg=Tq
bnRfdGg0dA==Tq
qsB6HTg=Tq
ckM1A+k=Tq
YjA5ODYxZg==Tq
lNFqHrA=Tq
fQ==Tq
p3z6PDU=Tq
YmhfNHJfNg==Tq
ETIPfVo=Tq
XzM0c3lfdA==Tq
zkc1rkc=Tq
ZdMoUG0=Tq
vid48FQ=Tq
ezF0X3c0cw==Tq
CKyQV00=Tq
Yw14dt4=Tq
Gy4DGUg=

┌──(mony㉿Mony)-[~/forensic]
└─$ echo "YWNhZGVteQ==" | base64 -d
echo "ezF0X3c0cw==" | base64 -d
echo "bnRfdGg0dA==" | base64 -d
academy{1t_w4snt_th4t
┌──(mony㉿Mony)-[~/forensic]
└─$ echo "XzM0c3lfdA==" | base64 -d
echo "YmhfNHJfNg==" | base64 -d
echo "YjA5ODYxZg==" | base64 -d
echo "fQ==" | base64 -d
_34sy_tbh_4r_6b09861f}
┌──(mony㉿Mony)-[~/forensic]
└─$
```



# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/