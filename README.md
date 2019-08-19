# Question to python-cec

Hi there,
i am using your repository python-cec to control my tv via a Raspberry PI with openhab. I use a SONY KDL 42W705B. It works quit well, i can turn on and off the tv and change the volume, for example with the command:
```python
cec.volume_up()
```
Now i want to change the channel and tried to use the command:
```python
cec.Device(cec.CECDEVICE_TV).transmit()
```

# Example
When i check on CEC-O-MATIC what i have to send to turn the tv off, the input has to be "10:36". With the command
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


When i try to use the funktion 
```python
destination = 0x0
opcode = 0x44
parameters = bytes([0x30])
cec.transmit(destination, opcode, parameters)
```
it just respons "true" but nothing happens.

You know what i am doing wrong? Thanks for your time and efford, Greetings Gideon
