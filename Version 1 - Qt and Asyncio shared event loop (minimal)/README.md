# Version 1 (basic)

![](../images/qt-wiretap.gif)

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

3. Run the NATS/QT wiretap.
``` bash
python nats_qt_wiretap.py localhost 4222 p1.s0
```
