# qt-python-nats-wiretap

Graphical wiretap utility based on NATS and QT.

* https://github.com/harvimt/quamash
* https://docs.python.org/3/library/asyncio.html
* https://nats.io/
* https://github.com/nats-io/nats-streaming-server#monitoring
* https://github.com/nats-io/asyncio-nats
* http://zetcode.com/gui/pyqt5/


## Basic functionality

1. Connect to NATS cluster.
2. Listen to NATS queue
3. Emit messages into a scrolling list box (list or table view).

## Notes
``` bash
pip install --upgrade pip' command
pip install quamash
pip install pyqt
pip install asyncio
pip install asyncio-nats-client

# To fire up the ui designer
designer

# To create python from ui files
pyuic5 main_window.ui > main_window.py

# To run Docker NATS image
docker run -p 4222:4222 -p 8222:8222 -p 6222:6222 --name gnatsd -ti nats:latest

```