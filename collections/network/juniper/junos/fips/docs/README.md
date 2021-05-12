Important Links:
  - https://www.juniper.net/documentation/us/en/software/vsrx/vsrx-kvm/vsrx-contrail/topics/task/security-vsrx-cloud-init-support.html
  - https://www.youtube.com/watch?v=FXXBEooil5s

LOCALHOST:SYSTEM: BEFORE_FIPS
```
[edit system login user vagrant authentication ssh-rsa]
  '"ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA6NF8iallvQVp22WDkTkyrtvp9eWW6A8YVr+kz4TjGYe7gHzIw+niNltGEFHzD8+v1I2YJ6oXevct1YeS0o9HZyN1Q9qgCgzUFtdOKLv6IedplqoPkcmF0aYet2PkEDo3MlTBckFXPITAMzF8dJSIFo9D8HfdOV0IAdx4O7PtixWKn5y2hMNG0zQPyUecp4pzC6kivAIhyfHilFR61RGL+GPXQ2MWZWFYbAGjyiYJnAmCP3NOTd0jMZEnDkbUvxhMmBYSdETk1rRgm+R4LOzFUGaHqHDLKLX+FIPKcF96hrucXzcWyLbIbEgE98OHlnVYCzRdK8jlqm8tehUc9c9WhQ== vagrant insecure public key"'
    Critical security parameter must be deleted before entering FIPS mode
[edit system root-authentication encrypted-password]
  'encrypted-password "$1$nq.N1UsY$JxA/ESAj3KuXseXE597gg0"'
    Encrypted-password must be re-configured to use FIPS compliant hash
[edit system root-authentication ssh-rsa]
  '"ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA6NF8iallvQVp22WDkTkyrtvp9eWW6A8YVr+kz4TjGYe7gHzIw+niNltGEFHzD8+v1I2YJ6oXevct1YeS0o9HZyN1Q9qgCgzUFtdOKLv6IedplqoPkcmF0aYet2PkEDo3MlTBckFXPITAMzF8dJSIFo9D8HfdOV0IAdx4O7PtixWKn5y2hMNG0zQPyUecp4pzC6kivAIhyfHilFR61RGL+GPXQ2MWZWFYbAGjyiYJnAmCP3NOTd0jMZEnDkbUvxhMmBYSdETk1rRgm+R4LOzFUGaHqHDLKLX+FIPKcF96hrucXzcWyLbIbEgE98OHlnVYCzRdK8jlqm8tehUc9c9WhQ== vagrant insecure public key"'
    Critical security parameter must be deleted before entering FIPS mode
error: commit failed: daemon file propagation failed

```

AFTER FIPS SETTING
```
vagrant@vsrx# commit 
Generating RSA key /etc/ssh/fips_ssh_host_key
Generating public/private rsa1 key pair.
Your identification has been saved in /etc/ssh/fips_ssh_host_key.
Your public key has been saved in /etc/ssh/fips_ssh_host_key.pub.
The key fingerprint is:
SHA256:s7RfX9smQCytv/3K5UEd7BpY2N7GXsiYCoqWtkxZWnI root@vsrx
The key's randomart image is:
+---[RSA1 2048]---+
|                 |
|            o .  |
|           + o o |
|          . B++.o|
|    . E S  =ooo*o|
|     X o =... * .|
|    O . o ...o oo|
|   = .   . ..+.+=|
|    o     . ..=*+|
+----[SHA256]-----+
Generating RSA2 key /etc/ssh/fips_ssh_host_rsa_key
Generating public/private rsa key pair.
Your identification has been saved in /etc/ssh/fips_ssh_host_rsa_key.
Your public key has been saved in /etc/ssh/fips_ssh_host_rsa_key.pub.
The key fingerprint is:
SHA256:G+MlAHYRBK6NoSHcWTyKXEOR4RYbMcMbbnngq0fEqKA root@vsrx
The key's randomart image is:
+---[RSA 2048]----+
|  oXX+=o         |
|. oXO=           |
|+.O*O o          |
|o*.# . .         |
|= = +   S .      |
|E  o   . *       |
|  o     o        |
| . .             |
|  .              |
+----[SHA256]-----+
Generating ECDSA key /etc/ssh/fips_ssh_host_ecdsa_key
Generating public/private ecdsa key pair.
Your identification has been saved in /etc/ssh/fips_ssh_host_ecdsa_key.
Your public key has been saved in /etc/ssh/fips_ssh_host_ecdsa_key.pub.
The key fingerprint is:
SHA256:SQ0q3Gt6ADSlKP9mOx6O7p67wBd0GD5lMRqVCXX1FbM root@vsrx
The key's randomart image is:
+---[ECDSA 256]---+
|  o==B+.o.   +.  |
| o.+B+o. o. . o  |
|o o*o.o . .. E   |
|....o. o .       |
|  ... o S        |
|.  ..+           |
|.. .* .          |
| ..*.+           |
| +O++.           |
+----[SHA256]-----+

```

COMMANDS:
  FILE SHOW:
    - user@host> file show /var/log/messages




    PSI-OSP-KEY-PAIR
    -----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAp1Cx4r/7KunHeYNabxCeIfflTRxWFKvUkebBdn+vyBJWEFsn
lrFkw6FrpSKZigO6zjxvMvYiKNkWkY8+KqLNQH+Fm2JztmS90nhSgGN/zA+juclF
7+7B0rUe/KdiMVTjkgeqQ5BA2D6SGHINJM+mOuia/ys/fQxN+qx8I7ERDsDcVPay
/ziVsqiy+mQo55g5lDC4hJ8jkwFOwk4rOEyigFSna5tiKtqasoKP15ErUk5OKjri
ZqCaP1ioDWYfCX6bOy0YRLHPTGfXyXiAXevd97efgHtffglkAgsNlEPnqCvM9Dxl
suud4o3HeZa3XlXISx+2NNJUsnGsamjR5U9bZQIDAQABAoIBAAvNbm7vWflh+ldB
A80X3//Ha95vpEbbBCiynW0NfsnfOUD4HSfNJa2DIoPImAobTz8jFjkDEc/N2IC2
GQ2K5G2rUTJv1HfGTXmeUTuLSUWMyODfKNbPAc8qRaBO8mdGdLMlZUZU064tY8Lj
sLerCi/Xnq9nTpg0mP+Y0Tz3TZu7s9WsUkv77/yDj/1qnZqX87JLvFSVlBeswgaj
GdtSblonzKj4yk+VNwrA1/b5Ciaw/khrYjsviDzbsfwRYypvWo25j7qJrOjz9gUb
ktoqHCe4sr/b20ceOD9BLnWNnZpA+zqq3DaZIfu9K7/cLXrcPBEBXbyLu8x0yM63
qvkK7BUCgYEA1+R9wykbCwH6wq2XfXo+NAQQr3+Uj1o1gXLnUd6ki0X1XqLbZgcN
KxarJuCf613+AMSjhu8UKncUtagB6CenqieM4C1KaVIIOd1UJHBSyI6mO2WhtUEF
v0vRqj7L7R6Ge8JOF4b+jFnyw99XaqzEZarv4l/vXu1PhNjDIEQtpdMCgYEAxmXx
ROA8cVvQaNpqfPSoePOOJFt8ubJolgYT7MN2fhU0/OCXfWumhyUfhjaDUq+j66L3
LQfs0lQlqk9/ZAXcM/c2QtQn6djg63Gso9HbZ9F1X2wpuuhfi9JxHIYHVjDm9yyc
IpDbJmrOGTJ6Xb9C7CooehK2+RUB94ff90CQHucCgYBcIDbCVwIhOmEFPgpNEyME
E1ADc8+zNG1spdmsB/PzMpE4Jwq0iQHHh07VsjjLuTownbiiVdcnH9WIhv75UCKt
616kMu9z7ftwpc/IFN5ekvDAm+fbbrnDHdmEanOe5c3BdfLY+1QYFDIR/3ZQIRVV
xRHEaee9fErYh58MX8uS3QKBgDP+TU9mkJCIpkKEUvnySCCCe5LNow8rUTtX1mrr
AqeiOSO4XBsTVi3+rZdHu/y0aPn82FglxouMX96VPOZinsXDmKXE4bzoCHHLdZnt
ClnXy7G5L+p6sWd8PAZknZGZ+T13pGdunPAhd2elEep1kD1CAx+Svf7i4YQUSL6M
XfirAoGAMK9MqsUHDAuXIiNjh4SHj4e2YRzkfKugmTtMA1bLRJZ9X00aCh+Vopyv
BQnPnRVvs8UkDW30RtF7rFwM3pboXAUdl9ilZB7ARVFmOC01tWeywjHD/dkbYelI
Zy/MrUNevHBmFesM1qPSwnSgQBYe1TJWpHiIq5YUlB0P3g6NjCM=
-----END RSA PRIVATE KEY-----