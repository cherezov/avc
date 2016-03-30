# avc
Python library to control Yamaha receivers over ethernet.

__in progress__

## Requires
* Python3 (Tested on Win7 python 3.4 for Yamaha RX-V577)

## TODO
- [ ] Consider python 2.7 support
- [ ] Test under linux
- [ ] Add SSDP discover 

## Usage
### As console app
#### Overview
```
avc.py [-i <ip> [power|mute] [on|off|toggle] | [list] [input|scene] [<value>] | volume [<value>]]
```

#### Discover
```
-- Discover all devices
> python avc.py 
Yamaha[ip='192.168.1.40', model='RX-V577']

-- Discover device by ip
> python avc.py -i 192.168.1.40 
Yamaha[ip='192.168.1.40', model='RX-V577']
```

#### On/off/toggle
```
-- Power on/off
> python avc.py -i 192.168.1.40 power on
Power on

> python avc.py -i 192.168.1.40 power toggle
Power off

-- Mute
> python avc.py -i 192.168.1.40 mute off
Mute off

> python avc.py -i 192.168.1.40 mute toggle
Mute on
```

#### List
```
> python avc.py -i 192.168.1.40 list input
HDMI4
AV1
AV6
HDMI3
HDMI6
AV5
HDMI1
HDMI2
USB
HDMI5
AV2
AV3
AV4
AUX

> python avc.py -i 192.168.1.40 list scene
Scene 1
Scene 2
Scene 3
Scene 4
```

#### Volume
```
-- Get current volume
> python avc.py -i 192.168.1.40 volume
-50.5dB

-- Volume up
> python avc.py -i 192.168.1.40 volume +1.5
-49dB
```

#### Input
```
-- Get current input
> python avc.py -i 192.168.1.40 input
HDMI1

-- Set input
> python avc.py -i 192.168.1.40 input AV1
AV1
```

#### Scene
```
TODO
```

### As python module
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
print(c.inputs)
#Output:
# {'HDMI4': 'HDMI4', 'TV': 'AV1', 'AV6': 'AV6', 'HDMI3': 'HDMI3', 'HDMI6': 'HDMI6', 'AV5': 'AV5', 'PC': 'HDMI1', 'HDMI2': 'HDMI2', 'USB': 'USB', 'HDMI5': 'HDMI5', 'AV2': 'AV2', 'AV3': 'AV3', 'AV4': 'AV4', 'AUX': 'AUX'}

# Set PC input
c.input = 'HDMI1'

```
