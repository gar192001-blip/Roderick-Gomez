# Roderick Gomez
- Universidad de Panamá
- Facultad de informática, electrónica y comunicación
- Asignatura: Metodos Numericos
- I semestre 
- Examen Semestral
- Profesor: Angel Avila
- Estudiante: Roderick Gómez 8-976-2162
- Fecha de entrega: 18 de junio 2026

## Seguimiento y evolución del T. Final (M. numéricos).  
# Trabajo Final
## Introducción
El codigo se basa en un software de una clinica de Terapia ocupacional Infantil,
la idea fue integrada gracias a la elaboracion de una clinica ficticia elaborada 
por mi pareja para un proyecto de terapia ocupacional en UDELAS, es un trabajo en conjunto donde se utilizara como complementacion para ambos, donde se evalua a sus pacientes y estar integradas partes como: registro,
evaluacion, calculo de progreso, programaccion de secciones de terapia, consulta de 
histortial y generacion de reporte operativo/financiero.
<img width="845" height="562" alt="image" src="https://github.com/user-attachments/assets/04d9b992-9601-4586-8915-37c794cc474f" />


## Codigo e imagen de copilacion 
## Los puntos en enfatizar son: 
- Funcion de la seccion.
- Metodos Aplicados y que funcion cumplio.
- Resultados a mostrar.

Punto importante!!
Al final del trabajo se dara la evolucion del progreso ficticio el paciente en la clinica, dada por el terapeuta
encargado de los resultados del sistema.

## Menu
El menu es el portal inicial, se encuentra las 7 secciones en este, donde el paso mas importante es registrar al cliente, en
los siguientes puntos estaremos integrando todos los metodos dados en clases aplicandolo a las necesidads de la clinica ficticia, exectuando los punto de cierre (7. Datos del software, y 0. Salida).
-  Evaluar progreso del paciente
-  Calcular medicion terapeutica
-  Programar sesion de terapia
-  Consultar historial de progreso
-  Generar reporte operativo y financiero

<img width="519" height="273" alt="image" src="https://github.com/user-attachments/assets/83676dc7-93d3-4699-b0c5-9737f2c28bf7" />

## Case 1 
- Funcion: permite registrar la información clínica inicial del paciente que será utilizada por el resto del sistema.
- Metodos y funcion: no tiene.
- Resultado: el paciente queda correctamente registrado y que todos los módulos posteriores utilizan sus datos reales.

<img width="513" height="234" alt="image" src="https://github.com/user-attachments/assets/4f1e82cd-30a9-4fd6-bb9a-0b247e2ed529" />


## Case 2
- Funcion: Ayuda a evaluar la estabilidad, la locomoción y la flexibilidad. Esto es gracias a un valor base obtenido, el cual se compara del 1 al 5 donde el valor más alto determina una mejor evolución en el paciente.
- Metodos y funcion:
  - Punto Fijo: evalua la estabilidad del movimiento del paciente mediante aproximaciones sucesivas.
  - Resultado: Con un valor inicial de 1.4, el método cambia rápidamente hacia: 1.41421
    
  - Newton-Raphson: calcula de manera rápida la tendencia de recuperación motora.
  - Resultado: el método cambia aproximadamente a: 1.41421
    
  - la Secante: calcula la evolución de la flexibilidad sin utilizar derivadas.
  - Resultado: cambia aproximadamente a: 2

- Entre los 3 permiten observar:
  - La estabilidad del movimiento.
  - Una estimación precisa del progreso.
  - La adaptación del paciente a la terapia.
 

<img width="582" height="343" alt="image" src="https://github.com/user-attachments/assets/9d52dde1-e967-4447-b3b5-bc2db1dc8fcc" />


## Case 3 
- Funcion: con esta seccion verifico la precisión de una medición realizada durante la terapia.
- Metodos y funcion:
- Error absoluto: determina cuántas unidades existe de diferencia entre lo esperado y lo obtenido
  - Resultado: existe una diferencia pequeña entre el objetivo clínico y la medición real.
    
- Error relativo: relaciona el error respecto al valor esperado.
  - Resultado: el paciente presenta solamente un 8% de diferencia respecto al objetivo terapéutico.

- Error porcentual: expresar el error en porcentaje para facilitar la interpretación clínica.
  - Resultado: el paciente ha alcanzado aproximadamente un 92% del objetivo terapéutico.

- Incertidumbre: determinar el margen de confianza de la medición.
  - Resultado: las mediciones poseen una variabilidad pequeña y aceptable.

<img width="504" height="249" alt="image" src="https://github.com/user-attachments/assets/2f84d2c5-6d75-43e2-a162-b78bc2a8e489" />


## Case 4 
- Funcion: ayudar al terapeuta a seleccionar el mejor horario para programar una sesión de terapia
- Metodos y funcion:
- Método de biseccion: ayuda a buscar el horario óptimo para la sesión terapéutica.
  - Resultado: es el horario mas adecuado para programar la terapia.

- Método de Falsa Posicion: Encontrar una alternativa de horario.
  - Resultado: Una segunda opción válida para la programación clínica.


<img width="494" height="352" alt="image" src="https://github.com/user-attachments/assets/4732ae89-1588-40d1-8543-f53e98fb26d4" />


## Case 5 

- Funcion: nos ayuda a ver el comportamiento de rexuperacion del paciente.
- Metodos y funcion:
- Método grafico: representar gráficamente la evolución del paciente. 
- Permite ver mayor fatiga en durante el tratamiento, menor fatiga entre el tratamiento, momento favorable de recuperacion.
  
<img width="619" height="426" alt="image" src="https://github.com/user-attachments/assets/f2408a81-b93e-41e2-bba7-437751051d31" />

- Funcion: nos ayuda a estimar que tan cerca es la evolucion real con respecto al comportamiento teorico esperado para un niño de su edad.
- Metodos y funcion:
- Error de formulación: comparar el comportamiento esperado según la edad con el progreso real del paciente.
  - Resultado: permite ver que la operacion coincide prácticamente con la evolución clínica observada, ya que solo existe una diferencia del 3%. 


<img width="601" height="313" alt="image" src="https://github.com/user-attachments/assets/ff61da60-866b-4c96-b2b7-0c158fcf1599" />


## Case 6
- Funcion: evalaa la precisión de los procesos de la clinica y optimiza la distribución de horas entre los especialistas.
- Metodos y funcion:
- Error propagado: calcular el error acumulado de los procesos administrativos.
  - Resultado: permite ver que la clínica posee un margen de error muy bajo en sus operaciones.

- Eliminacion Gaussiana: ayuda al sistema que distribuye las horas de trabajo entre los especialistas.
  - Resultado: Matriz triangular superior obtenida correctamente(Los datos fueron organizados correctamente para continuar con el cálculo).

- Metodo Gauss Jordan: Ayuda a optimizar la asignación de horas del personal.
  - Resultado: permite ver que los recursos de la clínica son suficientes para atender correctamente al paciente y mantener una planificación eficiente.


<img width="605" height="275" alt="image" src="https://github.com/user-attachments/assets/74d9ff23-f2e9-4815-ae0c-96083ef4a98d" />


## Case 7
- Funcion: presentala informacion general del proyecto y los 14 metodos implemntados:

1. Método de Punto Fijo
2. Método de Newton-Raphson
3. Método de la Secante
4. Error Absoluto
5. Error Relativo
6. Error Porcentual
7. Incertidumbre
8. Método de Bisección
9. Método de Falsa Posición
10. Método Gráfico
11. Error de Formulación
12. Error Propagado
13. Eliminación Gaussiana
14. Método de Gauss-Jordan

<img width="570" height="331" alt="image" src="https://github.com/user-attachments/assets/0f52c12d-09ee-4115-9f11-673187b96fa6" />


## Cierre del programa
- Funcion: finaliza la ejecución del sistema y cierra la sesión del usuario.
<img width="514" height="108" alt="Captura de pantalla 2026-07-19 132407" src="https://github.com/user-attachments/assets/a5ba7103-d22f-47a9-a451-eaf805cf7dd1" />

# Diagnostico Final del paciente
## En base a los datos dados y obtenidos por el sistema



Paciente: Roderick Gomez

Edad: 7 años

Diagnóstico inicial: Genu valgo (afectación en la rodilla).

## Resultados obtenidos durante la evaluación
### Se registró correctamente el paciente.
- El análisis mediante Punto Fijo, Newton-Raphson y Secante mostró una recuperación estable y una evolución favorable del movimiento.
- La medición terapéutica indicó una recuperación funcional del 92%, con un error absoluto de 8 unidades, un error relativo del 8% y una incertidumbre de ±4, lo que refleja una respuesta positiva al tratamiento.
- La programación automática recomendó un horario óptimo y una alternativa adecuada para las sesiones terapéuticas.
- El historial de progreso mostró una disminución de la fatiga durante la fase central del tratamiento y una evolución consistente con el peso del paciente.
- El error de formulación del 3% evidenció que la evolución clínica observada es muy cercana a la esperada para un niño de 7 años.
- El reporte operativo confirmó que la clínica cuenta con una distribución eficiente de recursos, asignando 2 horas al terapeuta físico, 3 horas al terapeuta motor y 1 hora al especialista en lenguaje, manteniendo un error operativo muy bajo (0.0583%).

## Diagnóstico Final

- Paciente pediátrico con genuvalgo en proceso de recuperación funcional favorable.

Los resultados obtenidos indican que el paciente presenta una evolución positiva, con una recuperación cercana al 92% de la capacidad funcional esperada, un 3% de diferencia respecto al modelo teórico para su edad y una respuesta satisfactoria al tratamiento. Se observa mejoría en la estabilidad, fuerza y movilidad de los miembros inferiores, por lo que se recomienda continuar con el plan de terapia fisica y ocupacional para fortalecer la musculatura, corregir progresivamente la alineación de las rodillas y consolidar una marcha completamente funcional.
