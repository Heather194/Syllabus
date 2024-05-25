# Actualizaciones Tarea

> 17-05-2024

1. En esta tarea, todos los archivos se deben abrir usando de encoding latin-1 .

> 17-05-2024

1. En los archivos `distritos.csv`, se eliminó un espacio en blanco presente al comienzo del nombre de algunas regiones y provincias del archivo. Esto es ya que se indicó que los archivos no tendrían errores de sintaxis. Esto evita que deban agregar algún tipo de procesamiento al nombre de las regiones y provincias para aprobar los tests. Quienes hayan agregado algún procesamiento para eliminar el espacio en los archivos, deberán revisar si siguen pasando los tests con este cambio. De la misma forma, el archivo `test_base_cargar_datos.py` fue actualizado para que el test de distritos no tenga los espacios en blanco.

2. En el archivo `test_13_max_locales_distrito.py`, en la función `test_3` se tenía un _typo_ en una de sus líneas. En particular, en la línea **140** se reemplazó:

    > `Distritos(id_distrito=1, nombre='Distrito 2',id_comuna=9,provincia='Macul',region= 'RM')`
    
   Por 
    
    >`Distritos(id_distrito=2, nombre='Distrito 2',id_comuna=9,   provincia='Macul',region= 'RM')`

	Y en la función `test_4`en la línea **182** se reemplazó: 

	> `Distritos(id_distrito=1, nombre='Distrito 2',id_comuna=9,provincia='Macul',region= 'RM')`
    
   Por 
    
    > `Distritos(id_distrito=2, nombre='Distrito 2',id_comuna=9,   provincia='Macul',region= 'RM')`

    
    Estos cambios, al ser solo de un test mal escrito, no debería modificar la solución de la evaluación.

3. En el archivo `test_04_especies_postulantes.py`, se reemplazaron las líneas que contenían el formato:
   > `self.assertIsInstance(resultado_estudiante, Generator)`

   Por

   > `self.assertIsInstance(resultado_estudiante, (list, tuple, set, filter, map, Generator))`

   Esto permite que el test apruebe en caso de retornar un map, filter, o estructura de datos creada con programación funcional. Quienes ya tengan ese test aprobado con su solución actual, este cambio no debería alterar en ninguna forma su respuesta actual (los tests deberían seguir pasando.)

4. En el archivo `consultas.py`, en la definición de la función `votos_interespecie`:

      ```
      > def votos_interespecie(generador_animales: Generator,
      >     generador_votos: Generator, generador_candidatos: Generator,
      >     misma_especie: bool) 
      ```
    Se agregó un `= False`en el parámetro `misma_especie`:
    
      ```
      > def votos_interespecie(generador_animales: Generator,
      >     generador_votos: Generator, generador_candidatos: Generator,
      >     misma_especie: bool = False,) -> Generator:
      ```
      Esto es ya que el enunciado indicaba que debía ir en la definición de dicha función. Esto hará que el código del `test_4` de `test_18_votos_interespecie.py` no se caiga por dicho problema. Se subió al syllabus un archivo `consultas.py` con el parámetro agregado en la función. Deben editar su `consultas.py` para incluir dicho argumento.

5. En el archivo `test_20_votos_validos.py`, en los tests existían instancias de animales con la especie `Pex dorado`, cuando debería ser `Pez dorado`. Se reemplazo el texto correspondiente. Esto hará que el código no se caiga en caso de encontrar una especie que no tiene conversión de edad en el generador de `ponderadores`, ya que es algo que el enunciado no pidió explicitamente.

> 20-05-2024

1. En los archivos `ponderadores.csv`, se eliminaron algunas especies duplicadas. De la misma forma, el archivo `test_solution.py` y `test_base_cargar_datos.py`fueron actualizados para que se tomen en cuenta estos cambios al momento de correr los tests. 
2. Se actualizó el enunciado agregando una línea al disclamer aclarando que los comandos que permitan crear o cambiar una estructura de dato a otra sin aplicar comprensión (o que no sean utilizadas dentro de un reduce o de una función
generadora) estarán prohibidas. 


> 22-05-2024
1. Se publicó el archivo `test_elementos_prohibidos.pyc` como apoyo para realizar la tarea.

2. Se modificó la consulta `distritos_mas_votos_especie_bisiestos()` para pedir de retorno los id de los distritos, en vez del nombre de los distritos.
  
3. Se actualizó `test_elementos_prohibidos.pyc` por un error detectado en la issue [405](https://github.com/IIC2233/Syllabus/issues/405).


> 23-05-2024
  
1. Se actualizó `test_elementos_prohibidos.pyc` por un error detectado en la issue [421](https://github.com/IIC2233/Syllabus/issues/421). Además, la version publicada del script era más estricta de lo indicado en el enunciado, se actualizño que relaja los criterios de `cargar_datos`. En caso de tener todo correcto con la version anterior, esto se mantendrá en la version nueva.

> 25-05-2024

1. Se agregaron nuevos test en los archivos `test_01_animales_que_votaron_por.py`, `test_06_votos_alcalde_en_local.py` y `test_16_mismo_mes_candidato.py` que **no contradice el enunciado**, pero es para que tengan un caso más para probar por consulta.

2. Se actualizaron los test `test_10_animal_mas_viejo_edad_humana.py`, `test_20_votos_validos.py`, `test_23_votos_validos_local.py` y `test_24_votantes_validos_por_distrito.py` para que la edad calculada se permita tanto por animal.edad como por 2024-año_nacimiento.

3. Se actualizó `test_14_votaron_por_si_mismos.py` se arregló para que el tipo de dato que retorne la consulta no sea únicamente un Generador, sino tambien aceptar, map, filter, etc.

4. Se actualizó `test_10_animal_mas_viejo_edad_humana.py` se arregló para que el tipo de dato que retorne la consulta no sea únicamente un Generador, sino tambien aceptar, map, filter, etc. Se arreglaron los atributos incorrectos de Local().

5. Se actualizó el `test_20_votos_validos.py` para que no hayan id_voto repetidos. 

6. Se actualizó `test_solution.py` para poder tener los resultados actualizados de los tests.

7. Se actualizó `test_elementos_prohibidos.pyc` por un error detectado en la issue [448](https://github.com/IIC2233/Syllabus/issues/448). En caso de tener todo correcto con la version anterior, esto se mantendrá en la version nueva.