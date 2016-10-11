# PHP-Extension-Modbus

Master functions

## modbus_open
modbus_open(string *$port*, int *$baud_rate*, char *$parity*, int *$bit_stop*, int *$time_out*);<br>
return __PORT__ reference<br>
_example_: $port = modbus_open("/dev/ttyUSB0", 38400, "N", 2, 50);

## modbus_close
_use_ : modbus_close(ref $port);<br>
$port = reference of modbus_open call

## modbus_read_holding_registers
_use_ : $v = modbus_read_holding_registers(ref *$port*, int *$id_slave*, int *$register*, int *$n_read*);<br>
$port = reference of modbus_open call<br>
$id_slave = number Id Node of the slave device<br>
$register = Register number start to read<br>
$n_read = how many registers reads (started from $register)<br>
<br>
_example_:<br>
$v = modbus_read_holding_registers($port, 28, 215, 4); // _read registers: 215, 216, 217 and 218_

## modbus_read_input_registers
_use_ : $v = modbus_read_input_registers(ref *$port*, int *$id_slave*, int *$register*, int *$n_read*);<br>
_read above_

## modbus_write
$r = modbus_write(int port, unsigned int device, unsigned int add, unsigned int len, unsigned int *dataw);<br>
(Need to improve it)
