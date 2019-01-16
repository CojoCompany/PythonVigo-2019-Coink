% La serpiente y el cerdito :snake: :pig:
% Clara Casas Castedo & Miguel Sánchez de León Peque
% 2019-01-17

El cerdito :pig:
================

Coink
-----

<video src="./videos/coink.gif" controls muted>
</video>

-------

![](./figures/hacksterio.png){width=100%}

[https://www.hackster.io](https://www.hackster.io)


Necesitaremos ...
-----------------

![](./figures/overall_coink.png){width=70%}

---

![](./figures/coink_build_inside.jpg){width=80%}


La serpiente :snake:
====================

Micropython
-----------

![](./figures/micropython-logo.svg){width=40%}


NodeMCU
-------

![](./figures/nodemcu.jpg)

---

![](./figures/nodemcu_pinmap.png)


I2C (comunicación sensor-micro)
-------------------------------

```python
from machine import I2C
from machine import Pin
i2c = I2C(scl=Pin(5), sda=Pin(4), freq=400000)
devices = i2c.scan()
print(devices)
```

WiFi (comunicación micro-PC)
----------------------------

Captura de datos del sensor
---------------------------

- tiempo total 1 segundo de datos
- 1000 lecturas por segundo
- sensor 3D con dimensiones x, y, z y tiempo

Manejo eficiente de memoria -> buffers + 'array'
------------------------------------------------

```python

x_array = array.array('h', (0 for i in range(num_measures)))
```
[https://docs.micropython.org/array](https://docs.micropython.org/en/latest/library/array.html#module-array)


Memoria vs tiempo de ejecución
------------------------------

```python
def read_coin(self):
        '''
        Read magnetic sensor values and save on RAM (arrays)
        '''
def save_readings(self):
        '''
        Save magnetic sensor values from RAM to a file
        '''
```

Buffer circular, la solución definitiva
---------------------------------------

```python
ring = array.array('h', (0 for i in range(4 * num_measures)))

def loop(self):
        ....
        position = i * 4
        ring[position] = time.ticks_us() % 65536
        ring[position + 1] = x
        ring[position + 2] = y
        ring[position + 3] = z
        .....
        urequests.post(url, data=bytearray(ring))

```

Analizando monedas
------------------

La nube con Flask
-----------------


¡Eso es todo!
=============

Fuentes
-------

- Código: [github.com/CojoCompany/coink](https://github.com/CojoCompany/coink/)
- Documentación:
[coink.readthedocs.io](https://coink.readthedocs.io/en/latest/)

¿Preguntas?
-----------
