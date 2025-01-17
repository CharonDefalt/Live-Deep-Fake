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
pip install requests urllib3 faker
```

# [!] Problem

There are currently some problems:
1. If yakit proxy is not used, uploading of malicious plug-ins will fail;
2. After the webshell is uploaded, if you want to make a post request, an error will be reported, as shown below:

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image-20240308230546869.png)

But this problem can also be solved. Just get the X-TC-CSRF-Token corresponding to the session id through a 403 error. For example, I uploaded the webshell ofbehinder3.0 and connected:

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image-20240308230808193.png)

3. There are still some details that need to be improved, such as the removal of malicious plugins, etc.If you have relevant coding skills, you can make pull requests.

# Vulnerability recurrence environment construction

Use docker to pull the vulnerable image and start it:

```shell
sudo docker pull jetbrains/teamcity-server:2023.11.3
sudo docker run -it -d --name teamcity -u root -p 8111:8111 jetbrains/teamcity-server:2023.11.3
# sudo ufw disable
```

Then make basic settings:

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image-20240307232348600.png)

![](https://raw.githubusercontent.com/W01fh4cker/blog_image/main/image-20240307232404056.png)



# Reference

https://www.rapid7.com/blog/post/2024/03/04/etr-cve-2024-27198-and-cve-2024-27199-jetbrains-teamcity-multiple-authentication-bypass-vulnerabilities-fixed/

https://github.com/Chocapikk/CVE-2024-27198
