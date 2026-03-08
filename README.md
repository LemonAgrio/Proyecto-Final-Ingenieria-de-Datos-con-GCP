# Proyecto-Final-Ingenieria-de-Datos-con-GCP
Una empresa del sector financiero opera actualmente bajo un modelo On-premise / Multicloud. Su sistema central genera datos de mercado críticos, pero carece de una infraestructura escalable en la nube para realizar análisis avanzado y visualización en tiempo real
## Problema
* **Latencia:** Imposibilidad de reaccionar a la volatilidad de activos (criptomonedas) en tiempo real.
* **Silos de Información:** Los datos están atrapados en el entorno local sin una ruta hacia un Data Warehouse analítico.
##Solucion
1. Extracción y Origen (Compute Engine + API)
Se configuró una instancia de VM que ejecuta un script de Python. Este script se conecta a una API financiera para obtener datos en tiempo real.

<img width="1355" height="1084" alt="image" src="https://github.com/user-attachments/assets/8194ee04-1961-4c37-bc81-9b44d13be106" />
