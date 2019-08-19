# Question to python-cec

Hi there,
i am using your repository python-cec to control my tv via a intel nuc with openhab. It works quit well, i can turn on and off the tv and change the volume, for example with the command:
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
cec.transmit(destination, opcode, parameters)
```
destination = 0x0
opcode = 0x44
parameters = bytes([0x30])
it just respons "true" but nothing happens.

You know what i am doing wrong? Thanks for your time and efford, Greetings

Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a sep

