login username: POP-101-ADMIN
login password: uZrt1E2ouhoZ
enable password: uZrt1E2ouhoZ

domain name: company.com
dmvpn target: pophub.company.com

3-digit telephony prefix: 101
-------------------------------
tui = 10100
ward hunt = 10101
admin hunt = 10102
hunt range = 10103 - 10109
audio page = 10110
autoreg range = 10111 - 10149
conf phone = 10150
admin phone = 10151 - 10160
manual range = 10161 - 10199

Subnets:
- full: 192.168.0.0/22
- data: 192.168.0.0/23
- special: 192.168.2.0/26
- voice: 192.168.2.64/26
- mgmt: 192.168.2.128/27
- optional: 192.168.2.160/28
- loopback: 192.168.2.176/28


Addressing on rtr:
- lb0: 192.168.2.177

Addressing on dsw:
- lb0: 192.168.2.178
- data_svi10: 192.168.1.254
- special_svi20: 192.168.2.62
- voice_svi30: 192.168.2.126
- mgmt_svi40: 192.168.2.158
- optional_svi50: 192.168.2.174

Addressing on wlc:
- data_svi10: 192.168.1.250
- special_svi20: 192.168.2.58
- voice_svi30: 192.168.2.122
- mgmt_svi40: 192.168.2.154
- mgmt_svi40_hex: C0A8029A
- optional_svi50: 192.168.2.170

Addressing on asw1:
- mgmt_svi40: 192.168.2.131

Addressing on asw2:
- mgmt_svi40: 192.168.2.132

Addressing on asw3:
- mgmt_svi40: 192.168.2.133

Addressing on asw4:
- mgmt_svi40: 192.168.2.134

Addressing on asw5:
- mgmt_svi40: 192.168.2.135



WLANs (SSID and PSK):
- data: POP-101-DATA / VlQ5548n
- special: POP-101-SPECIAL / SSVNeVE8
- voice: POP-101-VOICE / AntTfLJO
