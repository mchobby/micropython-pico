# micropython-pico : additional libraries for Raspberry-Pi Pico running under MicroPython

to be documented




# Libraries

The libraries must be copied on the MicroPython board before using the various examples.

On a WiFi capable plateform:

```
>>> import mip
>>> mip.install("github:mchobby/micropython-pico")
```

Or via the mpremote utility :

```
mpremote mip install github:mchobby/micropython-pico
```

What are the libraries:
* [`servo.py`](lib/servo.py) : offers the `Servo` class used to control servo-moteur.
* [`ultrasonic.py`](lib/ultrasonic.py) : offers the `Ultrasonic` class used to measure distances with a HC-SR04.
* [`buzzer.py`](lib/buzzer.py) : allows to play sound with a Piezo Buzzer (default on GPIO7).
* [`ws2812.py`](lib/ws2812.py) : use the WS2812 / NeoPixel Smart RGB leds (default on GPIO11).

# Servo motor

By default, the library generates a pulse between 1.0 to 2.0 ms (mid-point at 1.5ms) for an angle from 0 to 180°.

```>>> from servo import Servo
>>> s=Servo(10)
>>> s.angle(0)
>>> s.angle(90)
>>> s.angle(180)
```

Pulse values can be changed by calling the set calibration() method
```
# default calibration
s.calibration( 1.0, 2.0, 1.5, 0, 180 )
# SG92R calibratioin
s.calibration( 0.5, 2.5, 1.5, 0, 180 )
```

# Ultrasonic

An example is available in the following repository [pico-projects](https://github.com/mchobby/pico-projects) under the file [test_ultrasonic.py](https://github.com/mchobby/pico-projects/blob/main/07-servo-roulette/test_ultrasonic.py)

