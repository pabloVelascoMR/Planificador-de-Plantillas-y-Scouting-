# Planificador de Plantillas y Scouting | Unificación Algorítmica

## Objetivo del Proyecto

Este proyecto surge de una necesidad real en el ámbito del fútbol base: la planificación eficiente de la plantilla y la optimización de la red de ojeadores (scouters).

El objetivo principal fue demostrar la aplicabilidad y la unicidad de tres paradigmas algorítmicos fundamentales (Programación Dinámica, Dividir y Vencerás y Voraces) para transformar grandes volúmenes de datos (listas de jugadores y costes de desplazamiento) en planes de acción concretos y optimizados, sirviendo como un prototipo funcional para la gestión deportiva.

##  Problemas Resueltos

El proyecto aborda dos problemas principales en la gestión del equipo:

Selección Óptima de Jugadores (Plantilla Ideal): Obtener una lista de 23 jugadores de alto valor que cumpla estrictamente con las cuotas posicionales (3 Porteros, 5 Defensas, 10 Centrocampistas, 5 Delanteros).

Organización Eficiente del Scouting: Crear un plan de rutas de desplazamiento para los ojeadores que minimice la distancia total de viaje para cubrir todas las ciudades necesarias.

##  Algoritmos Implementados y Justificación

El proyecto implementa los tres algoritmos requeridos para abordar las diferentes fases de la planificación:

### Programación Dinámica (PD)

Función: mochilaParaJugadores()

Propósito: Se utiliza para resolver el Problema de la Mochila 0/1 Multidimensional. Su objetivo es seleccionar exactamente 23 jugadores maximizando la suma de sus valoraciones, bajo las restricciones obligatorias de cuota por posición (P<=3, D<=5, M<=10, F<=5).

Complejidad Temporal: $O(n \times 750)$.

Justificación: Se utiliza una tabla de cinco dimensiones (donde $n$ es el número de jugadores y $3 \times 5 \times 10 \times 5 = 750$ es el límite constante de posiciones). La complejidad es lineal respecto al número de jugadores ($n$) debido a que las dimensiones posicionales son constantes, asegurando la solución óptima que cumple todas las restricciones.

### Divide y Vencerás (Divide and Conquer - DyV)

Funciones: quicksort() y _quicksort()

Propósito: Una vez seleccionada la lista de 23 jugadores, se implementa una versión personalizada de Quicksort para ordenar la lista resultante de forma descendente por valoración. Esto permite al entrenador identificar rápidamente a los jugadores de más alto rendimiento, incluso si sus posiciones ya están cubiertas, facilitando decisiones de fichaje de "jugadores estrella".

Complejidad Temporal: $O(n \log n)$ (caso promedio).

Justificación: Se eligió Quicksort por su eficiencia y su capacidad de implementar un parámetro key_function personalizable, manteniendo la complejidad algorítmica clásica de este método.

### Algoritmo Voraz (Greedy)

Funciones: organizarScouting() y rutasParaScouter()

Propósito: Se utiliza el Algoritmo de Prim (un algoritmo voraz) para determinar la red de scouting. El objetivo es construir el Árbol de Expansión Mínima (MST) sobre el grafo de ciudades, conectando todas las ubicaciones al menor coste total de distancia posible, optimizando así los desplazamientos de los ojeadores.

Complejidad Temporal: $O(V^2)$.

Justificación: Esta implementación utiliza un enfoque más intuitivo al buscar el mejor candidato con min() en cada iteración, lo que resulta en una complejidad cuadrática respecto al número de vértices (ciudades, $V$). Esto garantiza que la ruta sea la más eficiente en coste.

## Uso e Instalación

Este proyecto se encuentra encapsulado en un Jupyter Notebook, que incluye el código, la documentación detallada y los tests unitarios.

Requisitos

Necesitas tener Python 3.x instalado en tu sistema.

Ejecución

Clona el repositorio:

git clone [https://github.com/tu-usuario/nombre-del-repo.git](https://github.com/tu-usuario/nombre-del-repo.git)
cd nombre-del-repo


Instala Jupyter (si no lo tienes):

pip install jupyter


Inicia Jupyter Notebook/Lab:

jupyter notebook

O bien: jupyter lab


Abre el archivo VelascoMartin_Opcional (2).ipynb y ejecuta las celdas secuencialmente.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.

## Autor

Pablo Velasco Martín
