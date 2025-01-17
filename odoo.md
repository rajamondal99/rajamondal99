==== To update all modules during development ====
```
--dev=all
```

=== How to check custom addons in odoo sh terminal ====
```
cd src/user
```


===How to install odoo in windows system. (for developer)========
```
https://www.cybrosys.com/blog/how-to-install-odoo-17-in-windowsHow to install the Odoo 17 in Windows 10/11

```


====Learn Odoo===
```
https://www.odoo.com/nl_NL/slides/partner-technical-training-introduction-to-development-318 
```


== How to run odoo from terminal==
```
python3 odoo-bin --addons-path=/odoo/odoo-server/addons,/odoo/custom/addons/test_cicd --http-port=8099 -d test -i royal_motorsc
```

===Odoo All Versions===
```
https://nightly.odoo.com/17.0/nightly/deb/
```

====How to know where is you python version files are =====
```
whereis python3.10
```
output:  """" python3.10: /usr/bin/python3.10 /usr/lib/python3.10 /etc/python3.10 /usr/local/lib/python3.10 /usr/include/python3.10 /usr/share/man/man1/python3.10.1.gz  """


=== How to install requirment.txt in specific python version ====

```
/usr/bin/python3.10 -m pip install -r requirements.txt

```

===Odoo RPC Docs====
```
https://www.odoo.com/documentation/17.0/developer/reference/external_api.html
```

=====Install========
https://github.com/Yenthe666/InstallScript

=====Session=========
If you want to set a value in the session , you can do it as follows,

request.session['val_name'] = value
To access the value which set in the session,

request.session['val_name']

====setup odoo in vsCode=====
{
        "version": "3.8",
        "configurations": [
            {
                "name": "Run Odoo",
                "type": "python",
                "request": "launch",
                "stopOnEntry": false,
                "console": "integratedTerminal",
                "python": "/usr/local/bin/python3.8", // cari dengan which python3
                "program": "/Users/sachinburnawal/Documents/odoo 13/source/odooitlunch/odoo/odoo-bin",
                "args": [
                    "--config=/Users/sachinburnawal/Documents/odoo 13/custom/odoo-addons-ilunch/odooee.conf",
                    // "--database=tutor1,tutor2",
                    // "--update=nama_folder1,nama_folder2"
                ]
            },
        ]
}


===debug xml ===
```
<t t-debug="pdb"/>
```

===AttributeError: module 'lib' has no attribute 'X509_V_FLAG_NOTIFY_POLICY'===
```
sudo rm -rf /usr/lib/python3/dist-packages/OpenSSL
sudo pip3 install pyopenssl
sudo pip3 install pyopenssl --upgrade
```


====Share filestore with multiple db======
```
sudo -u odoo ln -s /home/odoo/.local/share/Odoo/filestore/odoo_training /home/odoo/.local/share/Odoo/filestore/odoo

rm odoo/odoo_training

sudo -u odoo ln -s /home/odoo/.local/share/Odoo/filestore/odoo /home/odoo/.local/share/Odoo/filestore/odoo_training
```

==== run requirment.txt on multiple python version =====
```
python3.8 -m pip install -r requirements.txt
```

===CURL commend to backup database =====
```
curl -X POST -F 'master_pwd=mmmm' -F  'name=odoo16final' -F 'backup_format=sql' -o /opt/odoobella1.sql http://localhost:8069/web/database/backup
```


