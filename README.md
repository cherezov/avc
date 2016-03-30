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

# Set volume -50.5dB
c.volume = -50.5

# Volume up 1dB and down 2.5dB
c.volume += 1
c.volume -= 2.5

# Scenes and input mapping
print(c.scenes)
# Output: {'Scene 4': 'TUNER', 'Scene 2': 'AV1', 'Scene 1': 'HDMI1', 'Scene 3': 'NET RADIO'}

# Set NET RADIO scene
c.scene = 'Scene 3'

# Device inputs
print(c.intputs)
#Output:
# {'HDMI4': 'HDMI4', 'TV': 'AV1', 'AV6': 'AV6', 'HDMI3': 'HDMI3', 'HDMI6': 'HDMI6', 'AV5': 'AV5', 'PC': 'HDMI1', 'HDMI2': 'HDMI2', 'USB': 'USB', 'HDMI5': 'HDMI5', 'AV2': 'AV2', 'AV3': 'AV3', 'AV4': 'AV4', 'AUX': 'AUX'}

# Set PC input
c.input = 'HDMI1'



```
