#First run update and upgrade
```
sudo apt update && sudo apt upgrade -y
```
#Run requirment.txt file
```
pip3 install -r requirements.txt
```
or
```
sudo /usr/bin/python3.8 -m pip install -r requirements.txt 
```

##Make sure you have python-dev installed in your system

sudo apt install python<!your exact python version>-dev
```
 sudo apt install python3.6-dev
```

#Errors and Solution
  1. Failed building wheel for python-ldap:
  ```
  sudo apt-get install libsasl2-dev python3-dev libldap2-dev libssl-dev
  ```
  2. Failed building wheel for lxml:
  ```
  sudo apt-get install libslt-dev python3-dev
  ```
  3. Failed building wheel for pillow:
  
  ref:https://pillow.readthedocs.io/en/latest/installation.html
  ```
  sudo apt-get install libtiff5-dev libjpeg8-dev libopenjp2-7-dev zlib1g-dev \
    libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python3-tk \
    libharfbuzz-dev libfribidi-dev libxcb1-dev
  ```
  4. Failed building wheel for psycopg2:
  ```
  sudo apt-get update
  sudo apt-get install libpq-dev python3-dev
  ```
  5. Failed building wheel for wkhtmltopdf:
   
   ref: https://www.syntaxis.be/blog/the-blog-1/post/install-wkhtmltopdf-0-12-5-on-ubuntu-20-04-6
 
   #Download the package
     ```
     wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.bionic_amd64.deb
     ```
 
    #Install the package
      ```
      sudo dpkg -i wkhtmltox_0.12.5-1.bionic_amd64.deb
      ```
 
    #Fix dependencies
      ```
      sudo apt install -f
      ```
     
     
     
     
     
     
     
     
     
