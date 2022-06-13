---
layout:     post
title:      Flask-SocketIO使用
subtitle:   推荐工具
date:       2019-11-06
author:     JackyCJ
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Python
    - Flask-SocketIO

---



# Flask-SocketIO

```
pip install Flask-SocketIO
pip install websocket-client
```

- 报错  
The client is using an unsupported version of the Socket.IO or Engine.IO protocols (further occurrences of this error will be logged with level INFO)  
- 解决方案  
<font color=red>
Flask-SocketIO==4.3.1  
python-engineio==3.13.2  
python-socketio==4.6.0
</font>

## Version compatibility

The Socket.IO protocol has been through a number of revisions, and some of these introduced backward incompatible changes, which means that the client and the server must use compatible versions for everything to work.

The version compatibility chart below maps versions of this package to versions of the JavaScript reference implementation and the versions of the Socket.IO and Engine.IO protocols.  

| JavaScript Socket.IO version| Socket.IO protocol revision| Engine.IO protocol revision |	Flask-SocketIO version | python-socketio version |	python-engineio version|
|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:| 
|0.9.x |	1, 2 |	1, 2 |	Not supported |	Not supported| Not supported |
|1.x and 2.x |	3, 4 |	3 |	4.x |	4.x |	3.x|
|3.x and 4.x |	5 |	4 |	5.x |	5.x |	4.x|

# 参考

- [Flask-SocketIO](https://github.com/miguelgrinberg/Flask-SocketIO)
- [socket](https://cdn.socket.io/)
- [Introduction](https://flask-socketio.readthedocs.io/en/latest/intro.html#version-compatibility)
- [Python3+WebSockets实现WebSocket通信](https://www.cnblogs.com/lsdb/p/10949766.html)