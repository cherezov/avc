# avc
Python library to control Yamaha receivers over ethernet

__in progress__

## Require
* Python3

## Usage
```python
c = Avc('192.168.1.40')

# Toggle power
c.power = not c.power

# Mute
c.mute = True

# Get volume
print(c.volume)
#Output: -55dB

# Volume up 1dB and down 2.5dB
c.volume += 1
c.volume -= 2.5



```
