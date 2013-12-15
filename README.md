# Arduino TinyWire Slave Library

Originals from <http://www.arduino.cc/playground/Code/USIi2c>

Modified to support ATtiny44/84

## NOTE about reliable communication

Since (most of) the ATTinys lack TWI module for implementing all the nitty-gritty of I2C in hardware
they will have to do some clock-stretching (at least if run at 8MHz, you may get away with more on higher clock speeds)
as specified in the I2C protocol. However some (especially "bit-banged") master implementations do not
support clock-streching (looking at you Bus pirate 3.x and RPI), you will not get reliable communication
unless your master supports the full I2C protocol spec.

You can use my [Arduino based I2C master][i2crepl] to test your TinyWire code, this uses Bus Pirate semantics
with Arduinos TWI hardware that is known to implement I2C properly.

[i2crepl]: https://github.com/rambo/I2C/blob/master/examples/i2crepl/i2crepl.ino