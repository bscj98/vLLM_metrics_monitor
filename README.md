# Monitoreador de métricas de vLLM
Este proyecto consiste en, por medio de un servidor Prometheus, vincular las métricas del servidor 192.168.16.148:8000 a un dashboard de Grafana, así como generar alertas que notifiquen cuando las métricas se comportan de forma extraña. Las alertas son configuradas usando AlertManager.
## 1. Detalles del monitoreador
### 1.1. Servidor Prometheus
El servidor Prometheus conecta las métricas del vLLM con Grafana y AlertManager
#### 1.1.1. Parametros
1. scrape_interval: 5s. Frecuencia en la que Prometheus importa las métricas desde el vLLM
2. evaluation_interval: 30s. Frecuencia en la que Prometheus evalua las reglas de las alertas en alert_rules.yml
### 1.2. Dashboard
## 2. Lista de cambios para la implementación
### 2.1. templates/vllm_alerts.tmpl
1. Línea 77: {{ $grafana_url := "url del dashboard en Grafana" }}
2. Línea 78: {{ $prometheus_url := "url del servidor Prometheus" }}
### 2.2. alertmanager.yml
1. Línea 3: smtp_from: 'dirección de correo del emisor'
2. Línea 4: smtp_auth_username: 'dirección de correo del emisor'
3. Líneas 37, 45, and 53: - to: 'dirección de correo del receptor'
### 2.3. docker-compose.yml
1. Líneas 19, 29 y 35: Se pueden cambiar los puertos si hace falta
### 2.4 password.txt
Crear el archivo password.txt, que contenga el token de acceso a la cuenta de correo del emisor, en el directorio principal
