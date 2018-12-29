# Webgo

# Introduction
Using web browser to visit your computer which is running leela zero to analyse sgf.
So you can analyse all kifu anywhere.

![screenshot](screenshot/chinese.PNG)

# Dependency and acknowledge
1. Web page based on WGo.js.
2. Server side based on Leela Analysis Scripts and using python2.7
3. Server side also need Python module: bottle, gevent, gevent-websocket
4. Using some sabaki theme

# Server Installation
1. Install python 2.7
2. Install bottle, gevent, gevent-websocket
```
pip install bottle
pip install gevent
pip install gevent-websocket
```
3. If you already have your web server, please skip this step

There is already an internal web server together with Webgo.
The default listening port is 8000.
You can change it in svr/webgo.py.
```
httpdport = 8000
```

4. put all zip content to your web site root

If you are under windows platform, please run start.bat and you can change your favorite leela-zero in directory "dist".

In the example , it's ```c:\web```

# Server Configuration
In ```svr\webgo.py```, change to your own leelazero executable path and set the weight name correctly and make sure the leelaz.exe support lz-analyze gtp command
```
executable = "c:/go/leela-zero/leelaz.exe"
weight = '-wc:/go/weight/62b5417b64c46976795d10a6741801f15f857e5029681a42d02c9852097df4b9.gz'
```

# Sgf library
You can put sgf file under sgf directory

# How to run
server side, under cmd.exe run:
```
c:\python2.7\python webgo.py
```

browser side, can use pad/phone with any web browser
```
http://your_ip/webgo.html?sgf=1.sgf&move=50
```

# Using Webgo server in mac
1. Install brew using ruby
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
2. git clone branch
```
git clone -b next https://github.com/gcp/leela-zero.git
```
3. install boost
```
brew install boost
```
4. Compile leelaz with boardsize 9 or 19
5. using curl -O or ftp to get weight
6. full-tuner
7. install pip， bottle, gevent, gevent-websocket
```
sudo easy_install pip
sudo pip install bottle
pip install --user greenlet
pip install --user gevent
pip install --user gevent-websocket
```
If failed, maybe need to install pyenv, then using pyenv to install another version python
pyenv global 2.7.11 to switch version, but wish you lucky


# License

The code is released under the AGPLv3 or later.
