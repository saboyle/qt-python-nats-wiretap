# Version 1 (basic)

The basic gui wiretap combines the QT event loop with the Asyncio event loop and
updates a plain text edit box each time a new message is received
on a given queue.

The NATS server, port and queuename are specified on the command line.

Using the utility it is trivial to initiate multiple gui wiretaps to 
monitor intermediate queues within a distributed pipeline.

Each invocation of the wiretap will display a near native (windows/linux/osx) gui 
with low latency async updates each time a message is received.

![](../images/qt-wiretap.gif)

Note: currently the theme is hardcoded but can be easily configured using Qt stylesheets: https://doc.qt.io/qt-5/stylesheet-syntax.html. 

To execute open 3 terminals: 

1. Docker NATS server
``` bash
# To run Docker NATS image
docker run -p 4222:4222 -p 8222:8222 -p 6222:6222 --name gnatsd -ti nats:latest
```

2. Generate some test messages (publishes to localhost:4222 p1.s0)
``` bash
python nats_test_publisher.py
```

3. Run the NATS/Qt wiretap.
``` bash
python nats_qt_wiretap.py localhost 4222 p1.s0
```
## Possible Enhancements
* Buffer protection.
* Dynamic highlights based on regex.
* Configurable logging.
* Configurable storage of received messages to DB.
* Status bar showing connections.
* Incorporation into MDI NATS console.
* Pause scrolling.
* Double click on msg shows detailed view.
