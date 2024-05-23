# Could not execute command 'lessc'

The fix:

sudo apt-get install nodejs nodejs-legacy node-less
sudo apt-get install npm
sudo npm install -g less
sudo npm install -g less-plugin-clean-css
sudo ln -s /usr/local/bin/lessc /usr/bin/lessc
sudo ln -s /usr/bin/nodejs /usr/bin/node
After the fix you have 3 options (because a simply f5 to refresh or a server restart doesn't recompile your .less files):

1- Delete and/or Create a new Database

2- Install a module that add a new .less file to be compiled, like blog or website like was suggested here

3- Manually compile your .less files
