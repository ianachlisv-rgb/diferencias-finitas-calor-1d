# Conducción de calor 1D por diferencias finitas (Excel)

Libro de Excel con fórmulas para resolver  **−(k·T′)′ = H**  en una barra con 11 nodos:

- **Modelo**: datos editables (celdas amarillas: H, k, temperaturas de frontera, método, iteración a mostrar) y la gráfica.
- **Iteraciones**: Jacobi o Gauss-Seidel, hasta 1000 iteraciones.
- **Directo**: solución exacta del sistema tridiagonal (algoritmo de Thomas) para comparar.
- **Notas**: ecuación, fórmula por nodo y supuestos.

El ejemplo cargado es el de una clase: H = 500, 500, 0, 200, 0, 100, 100, 0, 400; k = 2; T(0) = 0 y T(1) = 25.
Gauss-Seidel desde 0 con 81 iteraciones reproduce la tabla del profesor; la solución convergida difiere unos 0.009.

`generar_excel.py` (necesita `openpyxl`) regenera el libro desde cero.

## Cómo usarlo
1. Abre `Diferencias_finitas_calor_1D.xlsx` y ve a la hoja **Modelo**.
2. Cambia solo las celdas amarillas: generación de calor `H` por nodo, conductividad `k`, temperaturas de frontera, método (Jacobi o Gauss-Seidel) e iteración a mostrar.
3. Compara la gráfica de la iteración elegida con la solución directa (hoja **Directo**): sirve para ver cuántas iteraciones necesita cada método para converger.

Para usar tus propios datos, sustituye `H` y `k`; el número de nodos (11) está fijo en el libro, y para cambiarlo hay que editar `generar_excel.py` y regenerarlo.

## Licencia
Código y hoja bajo licencia MIT (ver [`LICENSE`](LICENSE)).
