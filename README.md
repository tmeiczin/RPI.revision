# RPI.revision
Python library to retrieve revision and cpu information from a Raspberry Pi. This is based on the Raspberry Pi revision code schema:

https://github.com/raspberrypi/documentation/blob/develop/documentation/asciidoc/computers/raspberry-pi/revision-codes.adoc

## Install
```pip install RPi.revision```

## Usage

To get the revision object for the Raspberry Pi:
```
>>> from RPi.revision import CpuInfo, Revision
>>> revision = Revision()
>>> revision.memory
'2GB'
```

The object can be represented as a dictionary:
```
>>> from RPi.revision import CpuInfo, Revision
>>> revision = Revision()
>>> revision.asdict()
{'warranty': '0', 'new_flag': '1', 'memory': '2GB', 'manufacturer': 'Sony UK', 'processor': 'BCM2711', 'model': '4B', 'revision': '1'}
```

To decode any Raspbery Pi revision, it can be based into Revision upon instantiation:
```
>>> from RPi.revision import CpuInfo, Revision
>>> Revision(revision='9020e0').asdict()
{'warranty': '0', 'new_flag': '1', 'memory': '512MB', 'manufacturer': 'Sony UK', 'processor': 'BCM2837', 'model': '3A+', 'revision': '0'}
```

The CPU information can be retrieved:
```
>>> from RPi.revision import CpuInfo, Revision
>>> CpuInfo().asdict()
{'hardware': 'BCM2835', 'serial': '10000000a311552c', 'revision': 'b03111', 'model': 'Raspberry Pi 4 Model B Rev 1.1', 'cpu_count': 4}
```
