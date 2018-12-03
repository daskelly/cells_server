# Notes during build process

```
ssh <cells>
```

```
CentOS Linux 7
sudo yum -y update
useradd example_user && passwd example_user
sudo yum -y install httpd
sudo cp /etc/httpd/conf/httpd.conf /etc/httpd/conf/httpd.conf.original
sudo yum -y install emacs
```

# Bash profile

Add the following text to `~/.profile`.
```
if [ -f ~/.bashrc ]; then
        . ~/.bashrc
fi
```

# Sample HTML

```
sudo emacs -nw /var/www/html/sample.html
```

Add the following text
 
```
<!DOCTYPE html>

<!--
Copyright 2015 Google Inc.
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at
     http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

<html>

<head>
    <title>Hello, world</title>
    <link rel="stylesheet" href="/style.css">
    <script src="/script.js"></script>
</head>

<body>
    <h1>Hello, world</h1>

    <button onclick="fetchMessage()">Fetch Message</button>
    <p id="message">Click on the button to fetch the message.</p>
</body>

</html>
```

Modify httpd.conf with your document root directory to point Apache to your site’s files - I am 
using default dir /var/www/html.

Restart apache:
```
sudo systemctl enable httpd.service
sudo systemctl restart httpd.service
```

Install and run a demo of CellBrowser
```
sudo yum -y install python-pip
sudo pip install cellbrowser
cd; curl -s https://cells.ucsc.edu/downloads/samples/mini.tgz | tar xvz
cd mini
cbBuild -o ~/public_html/cells/ -p 8888
```

Go to IP_address:8888.

# Developing a demo served by Apache

```
sudo yum install mosh
sudo pip install --upgrade pip
sudo pip install numpy
```

Added `CBOUT` to `~/.bashrc`.

For some reason cbBuild with `-o $CBOUT` trying to serve with Apache doesn't seem to be working ...
