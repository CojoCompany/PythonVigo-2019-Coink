% La serpiente y el cerdo :snake: :pig:
% Clara Casas Castedo & Miguel Sánchez de León Peque
% 2017-11-23

El cerdo :pig:
==============

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


La serpiente :snake:
====================

Micropython
-----------

![](./figures/nodemcu.jpg)


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

¿Esto es python o C?
--------------------

```python
ring = array.array('h', (0 for i in range(4 * num_measures)))
position = i * 4
ring[position] = time.ticks_us() % 65536
ring[position + 1] = x
ring[position + 2] = y
ring[position + 3] = z
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
