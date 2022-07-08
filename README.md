# RPA-Developer-Examples-Listas

Recapitulemos las actividades y los métodos utilizados

Comenzamos el proyecto como una secuencia y creamos 2 variables de lista ("CiudadesEspaña" y "CiudadesRU").

Puesto que las variables Collection tienen que ser instanciadas y rellenadas con valores, hemos usado 2 métodos diferentes:

Para "CiudadesEspaña", creamos una instancia y rellenamos la Lista desde el panel Variables, utilizando la expresión new List (of String) from {"MADRID","valencia", "BARCELONA"};

Para "CiudadesRU", creamos una instancia de la lista desde el Panel de variables utilizando la expresión new List (of String) y la rellenamos mediante las actividades "Añadir a la colección".

Combinamos las 2 variables "Lista" en una variable "Lista" recién creada ("TodasLasCiudades"), usando el método Enumerable.Concat dentro de una actividad Asignar. Hemos utilizado la expresión Enumerable.Concat(SpainCities.AsEnumerable, UKCities.AsEnumerable).ToList. 

.AsEnumerable se utiliza para convertir las 2 Listas al tipo de datos Enumerable, y luego .ToList convierte el resultado en List.

Usamos Invocar método para ordenar los elementos de la lista de resultados seleccionando Ordenar en el campo campo MethodName.

Usamos una actividad Para cada para pasar por los elementos de la variable "AllCities" y:

Los convertimos en ProperCase usando el método StrConv: StrConv(item, VbStrConv.ProperCase);

Agregamos los elementos convertidos a una variable Lista recién creada ("AllCitiesProperCase") utilizando la actividad Añadir a colección.

Usamos una actividad Escribir línea para visualizar los valores convertidos utilizando el método String.Join: String.Join(",",AllCitiesProperCase).