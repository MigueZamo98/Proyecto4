---

## Universidad de Costa Rica
### Escuela de Ingeniería Eléctrica
#### IE0405 - Modelos Probabilísticos de Señales y Sistemas

---
### Proyecto 4

* Estudiante: **Miguel Zamora Torres**
* Carné: **B78542**
* Grupo: **2**
### Segundo Semestre 2021
---

### Documentación de la solución

Para la primera parte, se llevó acabo la simulación del sistema de comunicaciones utilizando una modulación 16-QAM, para el cual se tomó como base el documento P4.ipynb dado por el profesor donde se definián las funciones llamadas fuente_info, rgb_a_bit, bits_a_rgb y canal_ruidoso, estas funciones se mantuvieron tal cual las definió el profesor ya que nos servían.

Para la función llamada *modulador* se crearon dos distintas portadoras, una para I y otra para Q. La lógica utilizada para realizar en análisis de los bits en grupos de 4 en 4 (y moduladorlos tanto para I como para Q según correspondiese) fue utilizar la función range para lograr realizar la separación en grupos de 4, luego se aplica un for en donde se hace el análisis de cada grupo de bits gracias a la comparación con dos variables nuevas creadas, después de este for se realiza el cálculo de la potencia promedio acumulada de la señal modulada para obtener el promedio y la autocorrelación temporal. Finalmente se retornan la señal_Tx, Pm, portadora (suma de la portadorea I y Q) y la moduladora.

En la función *canal_ruidoso* se recibe la señal senal_Tx, la potencia promedio de la señal modulada y la relación señal-a-ruido del canal. A partir de este último parámetro se calcula la potencia del ruido generado por el canal de acuerdo con la fórmula vista en la nota teórica.

Para la función llamada *demodulador* se crea un vector para la señal demodulada, el procedo de demodulación aplica un for en los vectores producto y señal demodulada para lograr hacer el análisis según la pseudo-energía (Ep) de la portadora en un período, donde se aplica el criterio de demodulación según el intervalo de Ep en que se encuentre.

Finalmente se le brinda la frecuencia de la portadora (en este caso se asigna 5kHz), el número de muestras por periodo (20) y la relación señal ruido (SNR) que en este caso se le asignó un valor de 35, lo que quiere decir que la potencia de la señal y la potencia del ruido poseen una ligera diferencia. Las imágenes transmitida y recibida fueron las siguientes, con un total de al rededor de 500 errores para un BER = 0.

