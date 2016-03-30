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

# Scenes and input mapping
print(c.scenes)
# Outpu: {'Scene 4': 'TUNER', 'Scene 2': 'AV1', 'Scene 1': 'HDMI1', 'Scene 3': 'NET RADIO'}

# Set NET RADIO scene
c.scene = 'Scene 3'



```
