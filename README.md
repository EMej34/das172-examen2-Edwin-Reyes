# Examen 2 - Balance de Carga en Aeronaves  
**Repositorio:** das172-examen2-Edwin-Reyes  

## Introducción
Este proyecto implementa un sistema modular en Python para analizar la distribución de cargas en aeronaves.  
El objetivo es validar matrices de carga y capacidad, calcular porcentajes de ocupación, evaluar el balance lateral y longitudinal, y detectar submatrices críticas con mayor ocupación.  

---

## Objetivos
1. Validar que las matrices de cargas y capacidades sean coherentes.  
2. Calcular porcentajes de ocupación y detectar sobrecargas.  
3. Evaluar el balance lateral y longitudinal con tolerancia definida.  
4. Extraer la submatriz crítica con mayor promedio de ocupación.  
5. Incluir pruebas unitarias para verificar el correcto funcionamiento de cada módulo.  

---

##  Diagrama Modular
                ┌───────────────────────┐
                │     validacion.py     │
                │  Verifica dimensiones │
                └───────────┬───────────┘
                            │
                ┌───────────▼───────────┐
                │     ocupacion.py      │
                │  Calcula % ocupación  │
                │     y sobrecargas     │
                └───────────┬───────────┘
                            │
                ┌───────────▼───────────┐
                │      balance.py       │
                │ Evalúa balance lateral│
                │   y longitudinal      │
                └───────────┬───────────┘
                            │
                ┌───────────▼───────────┐
                │     submatriz.py      │
                │   Extrae submatriz    │
                │   crítica (mayor % )  │
                └───────────┬───────────┘
                            │
                ┌───────────▼───────────┐
                │       main.py         │
                │    Integra módulos y  │
                │   ejecuta resultados  │
                └───────────┬───────────┘
                            │
                ┌───────────▼───────────┐
                │        tests/         │
                │ Pruebas unitarias     │
                │ Casos típicos y borde │
                └───────────────────────┘
  ## Complejidad Computacional

Cada módulo del sistema tiene una complejidad distinta, pero en general el algoritmo es eficiente y escala de manera lineal con el tamaño de la matriz:

- **Validación de dimensiones:**  
  Recorre todas las filas y columnas → **O(N × M)**

- **Cálculo de ocupación:**  
  Calcula porcentajes para cada celda → **O(N × M)**

- **Evaluación de balance:**  
  Suma pesos por filas y columnas → **O(N × M)**

- **Submatriz crítica:**  
  Busca todas las posibles submatrices de tamaño `k × p` →  
  **O((N-k+1) × (M-p+1) × k × p)**  
  En el peor caso, se aproxima a **O(N × M × k × p)**

En conjunto, el sistema es **lineal respecto al tamaño de la matriz**, cumpliendo con los requisitos de eficiencia para aplicaciones en ingeniería.

---

## Casos de prueba incluidos

Se implementaron pruebas unitarias para verificar el correcto funcionamiento de cada módulo, tanto en **casos típicos** como en **casos de borde**:

- **Validación correcta:** matrices coherentes.  
- **Dimensiones incorrectas:** filas/columnas desiguales.  
- **Valores inválidos:** cargas negativas o capacidades ≤ 0.  
- **Ocupación normal:** porcentajes ≤ 100%.  
- **Ocupación con sobrecarga:** porcentajes > 100%.  
- **Balance equilibrado:** diferencia dentro de tolerancia.  
- **Balance desequilibrado:** diferencia fuera de tolerancia.  
- **Submatriz crítica:** selección de la región con mayor promedio.  
Nombre: Reyes Mejia, Edwin Mauricio 
Curso: DAS172
Examen: 2



