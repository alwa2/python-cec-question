# Question to python-cec

Hi there,
i am using your repository python-cec to control my tv via a intel nuc with openhab. It works quit well, i can turn on and off the tv and change the volume with the command:
```python
cec.volume_up()
```
Now i want to change the channel and tried to use the command:
```python
cec.Device(cec.CECDEVICE_TV).transmit()
```
but i don't realy know how to use it or if i have to use the command:
```python
cec.transmit(destination, opcode, parameters)
```
for it

# Example
When i check on CEC-O-MATIC what i have to send to turn the tv off, the input has to be "10:36". Whith the command
```python
cec.Device(cec.CECDEVICE_TV).transmit(0x36)
```
it works.

To change the the channel up the input has to be "10:44:30"
When i try:
```python
cec.Device(cec.CECDEVICE_TV).transmit(0x44, 0x30)
```
it gives me an Error that the second argument has to be a string.
When i try:
```python
cec.Device(cec.CECDEVICE_TV).transmit(0x44, "Channel Up")
```
it mutes my tv.



