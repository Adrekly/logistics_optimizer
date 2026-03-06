# 🚚 Proyecto III: Logistics Optimizer (Smart Routing)

[cite_start]**Universidad Nacional Experimental de Guayana (UNEG)** 
[cite_start]**Asignatura:** Sistemas de Bases de Datos II 
[cite_start]**Profesora:** Clinia Cordero   

## 👥 Equipo de Desarrollo
* Adrián Reina
* Sebastián Rodríguez
* Eldry Valderrey

---

## 🎯 Objetivo del Proyecto
Este repositorio contiene la implementación de un sistema de gestión de logística en base de datos de grafos orientado a la optimización de rutas de entrega. El sistema calcula la ruta más eficiente considerando variables dinámicas del mundo real como la distancia, el tiempo estimado, el estado del tráfico y la capacidad de carga de las vías.

## 🛠️ Tecnologías y Librerías Utilizadas
* **Motor de Base de Datos:** Neo4j Desktop
* **Lenguaje de Consultas:** Cypher nativo avanzado (Uso de `WITH`, `UNWIND`).
* **Librerías Obligatorias:** Graph Data Science (GDS) y APOC.
* **Visualización:** NeoDash (Neo4j Browser).
---

## 🚀 Desafíos Técnicos Resueltos
1. **Cálculo Matemático de Costos:** Función implementada en Cypher para determinar el costo de la ruta mediante la fórmula: `Costo = Σ (distancia * factor_trafico)`.
2. **Restricciones de Carga (Filtrado Dinámico):** Evaluación en tiempo real para deshabilitar rutas que no soportan el peso en toneladas de un camión asignado
3. **Smart Routing (Dijkstra vs A*):** Comparación directa del algoritmo Dijkstra (basado en peso de distancia) frente a A-Star (basado en heurística espacial de tiempo y tráfico) utilizando la librería GDS.

---

## 📂 Estructura del Repositorio
* `carga_datos.cypher`: Script principal o "Dump" de la BD para replicar el escenario exacto con los nodos (Almacén, Intersecciones, Punto de Entrega) y relaciones (`CONECTA_A`).
* `diccionario_consultas.txt` / `.cypher`: Documento con las 5 consultas complejas exigidas para la evaluación técnica.
* `informe_tecnico.pdf`: Documento con el diagrama del modelo y la justificación técnica de por qué Neo4j es superior a SQL para este caso de uso.

---

## ⚙️ Instrucciones de Instalación y Ejecución
Para replicar y evaluar este entorno localmente, siga estos pasos:

1. Clonar este repositorio.
2. Abrir **Neo4j Desktop** y crear una base de datos local nueva.
3. En la pestaña de *Plugins* de la base de datos, instalar **Graph Data Science Library** y **APOC**.
4. Iniciar la base de datos y abrir el **Neo4j Browser**.
5. Copiar el contenido completo del archivo `carga_datos.cypher` y ejecutarlo en la consola para poblar el mapa.
6. Ejecutar individualmente las consultas del diccionario para probar las restricciones, la proyección en memoria y los algoritmos de enrutamiento.
