# readme
Este proyecto consiste en, por medio de un servidor Prometheus, vincular las métricas del servidor 192.168.16.148:8000 a un dashboard de Grafana, así como generar alertas que notifiquen cuando las métricas se comportan de forma extraña. Las alertas son configuradas usando AlertManager.
## 6. Lista de cambios para la implementación
### 6.1. templates/vllm_alerts.tmpl
1. Línea 77: {{ $grafana_url := "url del dashboard en Grafana" }}
2. Línea 78: {{ $prometheus_url := "url del servidor Prometheus" }}
### 6.2. alertmanager.yml
1. Línea 3: smtp_from: 'dirección de correo del emisor'
2. Línea 4: smtp_auth_username: 'dirección de correo del emisor'
3. Líneas 37, 45, and 53: - to: 'dirección de correo del receptor'
### 6.3. docker-compose.yml
1. Líneas 19, 29 y 35: Se pueden cambiar los puertos si hace falta
### 6.4 password.txt
Crear el archivo password.txt, que contenga el token de acceso a la cuenta de correo del emisor, en el directorio principal
