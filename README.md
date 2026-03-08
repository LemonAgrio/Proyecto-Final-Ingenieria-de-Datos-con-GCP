# Proyecto-Final-Ingenieria-de-Datos-con-GCP
Una empresa del sector financiero opera actualmente bajo un modelo On-premise / Multicloud. Su sistema central genera datos de mercado críticos, pero carece de una infraestructura escalable en la nube para realizar análisis avanzado y visualización en tiempo real
## Problema
* **Latencia:** Imposibilidad de reaccionar a la volatilidad de activos (criptomonedas) en tiempo real.
* **Silos de Información:** Los datos están atrapados en el entorno local sin una ruta hacia un Data Warehouse analítico.
##Solucion
* **Extracción y Origen (Compute Engine + API)** 
Se configuró una instancia de VM que ejecuta un script de Python. Este script se conecta a una API financiera para obtener datos en tiempo real.

Instalamos las herramientas de entorno virtuales:

<img width="1355" height="1084" alt="image" src="https://github.com/user-attachments/assets/8194ee04-1961-4c37-bc81-9b44d13be106" />

* **Creamos La carpeta y nos conectamos a la API**
<img width="2535" height="1535" alt="image" src="https://github.com/user-attachments/assets/904d9791-9f08-4d1b-bb6b-9dcacd03a57c" />

* **Creamos el archivo principal.py en el cual colocameros nuestro codigo**
<img width="2558" height="1598" alt="image" src="https://github.com/user-attachments/assets/6818f4d4-d17d-4a18-b539-b1074918af4a" />

### Respaldo de los datos obtenidos

Se configuró un bucket en Cloud Storage para el almacenamiento de los archivos JSON originales, garantizando un histórico inalterable de los datos ingeridos a través de la API.4
<img width="2552" height="1331" alt="image" src="https://github.com/user-attachments/assets/d45329af-052b-4ceb-aa73-45219558e9d5" />

### Mensajería (Pub/Sub)

Se ha implementado una arquitectura de desacoplamiento de componentes mediante el uso de Pub/Sub - BigQuery. Este servicio gestiona el flujo de eventos entre la extracción y el almacenamiento, asegurando la integridad de los mensajes y permitiendo una ingesta asíncrona hacia Bigquery

<img width="2551" height="1324" alt="image" src="https://github.com/user-attachments/assets/7aa15c47-2ea5-43a8-b0fd-a55f2fffdba6" />

### Almacenamiento Analítico (BigQuery)

Como etapa final del pipeline, se implementó un Data Warehouse en BigQuery, estructurado mediante el conjunto de datos stock_analysis y la tabla cryptostreaming.

<img width="2553" height="1334" alt="image" src="https://github.com/user-attachments/assets/f2032cc6-c31f-4c91-953a-d2da46df9515" />

### Implementación y Ejecución del Pipeline:
Una vez configurado el entorno virtual (venv_sd), se procedió a la integración del script de Python con la infraestructura de GCP. Se actualizó el código con el Topic ID correspondiente de Cloud Pub/Sub y se ejecutó el proceso para iniciar la ingesta de datos financieros en tiempo real hacia la nube.

<img width="2548" height="1441" alt="image" src="https://github.com/user-attachments/assets/34379052-46ba-4edc-a6bd-5558545803f8" />
