# SHT30 Linux Python driver for Raspberry PI

It was tested on Raspberry Pi4 only.
If you have i2c issues on Raspberry, please make i2c baud rate slower, it helps.
Original driver based on [micropython-sht30](https://github.com/rsc1975/micropython-sht30), but significantly rewritten and ported for Raspberry.

## References:

* [Sensor Datasheet](https://static.chipdip.ru/lib/994/DOC003994445.pdf)
* [Arduino driver](https://github.com/wemos/WEMOS_SHT3x_Arduino_Library)

## Examples of use:
Basic usage:

```python
import sys
import SHT30 as driver

sensor = driver.SHT30()
if not sensor.is_plugged():
    print("SHT30 is not plugged!")
    sys.exit(1)
temperature, humidity = sensor.measure()
print('Temperature:', temperature, 'ºC, RH:', humidity, '%')
print(sensor.status())
```

[Full hands-on example in file utils/measure.py](utils/measure.py)
