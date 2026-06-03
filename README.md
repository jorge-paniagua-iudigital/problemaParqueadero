# Simulación Estocástica del Sistema de Pago de Parqueaderos — Supercentro

Este repositorio contiene el desarrollo del laboratorio final de modelado y simulación de eventos discretos enfocado en la evaluación operativa y el análisis de estabilidad del sistema de cajeros de pago de parqueaderos en el Centro Comercial Supercentro.

## Archivo del Proyecto
* **`Paniagua_Jorge_problemaParqueadero.ipynb`**: Código fuente e informe técnico integrado desarrollado en Google Colab utilizando Python. Incluye la implementación de las colas exponenciales, rutinas de calibración, algoritmos de promedio móvil para filtrado transitorio y visualización avanzada de métricas con Matplotlib.

## Resumen del Diagnóstico Operativo
A través de una simulación masiva de **5,111 clientes registrados**, el modelo determinó un diagnóstico crítico de ingeniería:
* **Inestabilidad del Sistema ($\rho \approx 1.21$):** Al analizar el reparto equitativo del flujo, cada cajero independiente experimenta una tasa de llegada superior a su tasa media ponderada de servicio, rompiendo la condición de estabilidad de la teoría de colas ($\rho < 1$).
* **Cuello de Botella:** La saturación extrema provoca que las colas diverjan linealmente hacia el infinito con el paso del tiempo, provocando tiempos medios de permanencia en el sistema de **~480 minutos** (aproximadamente 8 horas). Esto supera de manera catastrófica el límite máximo aceptable de 8 minutos.
* **Neutralización de Perfiles:** Se identificó que en un sistema saturado, el gigantesco tiempo de espera en la fila ($W_q$) absorbe y homogeneiza el impacto temporal sobre el cliente, volviendo despreciable e invisible la diferencia neta entre un usuario "Rápido" (1 min de atención) y uno "Muy Lento" (6 min de atención).
