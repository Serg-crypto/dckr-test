
# Variables
REDIS_TAG=3
REDIS_CONTAINER_NAME=redisTest
REDIS_IMAGE_NAME=redis


build_monitor_prometheus:
	@echo 'Construccion y despliegue de Prometheus'
	cd monitor/prometheus && docker-compose up -d 

build_monitor_grafana:
	@echo 'Construccion y despliegue de Grafana'
	cd monitor/grafana && docker-compose up -d

build_monitor_redis:
	@echo 'Construccion y despliegue de redis'
	cd monitor/redis && docker-compose up -d

build_monitor_redis_exporter:
	@echo 'Construccion y despliegue de redis-exporter'
	cd monitor/redis-exporter && docker-compose up -d

build_monitor: ## Construccion del monitor
	@echo 'Contenedores en ejecucion'
	docker ps
	$(MAKE) build_monitor_prometheus
	$(MAKE) build_monitor_grafana
	$(MAKE) build_monitor_redis
	$(MAKE) build_monitor_redis_exporter
	@echo 'Contenedores en ejecucion'
	docker ps 



# DETENER LOS SERVICIOS DE MONITOREO

stop_monitor_prometheus:
	@echo 'Detener el servicio de Prometheus'
	cd monitor/prometheus && docker-compose stop prometheus

stop_monitor_grafana:
	@echo 'Detener el servicio de Grafana'
	cd monitor/grafana && docker-compose stop grafana

stop_monitor_redis:
	@echo 'Detener el servicio de redis'
	cd monitor/redis && docker-compose stop redis

stop_monitor_redis_exporter:
	@echo 'Detener el servicio de redis-exporter'
	cd monitor/redis-exporter && docker-compose stop redis-exporter

stop_monitor: ## Detener los servicios del monitor
	@echo 'Contenedores en ejecucion'
	docker ps
	$(MAKE) stop_monitor_prometheus
	$(MAKE) stop_monitor_grafana
	$(MAKE) stop_monitor_redis
	$(MAKE) stop_monitor_redis_exporter
	@echo 'Contenedores en ejecucion'
	docker ps 




# ELIMINAR LOS SERVICIOS DE MONITOREO
down_monitor_prometheus:
	@echo 'Eliminar el servicio de Prometheus'
	cd monitor/prometheus && docker-compose down prometheus

down_monitor_grafana:
	@echo 'Eliminar el servicio de Grafana'
	cd monitor/grafana && docker-compose down grafana

down_monitor_redis:
	@echo 'Eliminar el servicio de redis'
	cd monitor/redis && docker-compose down redis

down_monitor_redis_exporter:
	@echo 'Eliminar el servicio de redis-exporter'
	cd monitor/redis-exporter && docker-compose down redis-exporter


# Contenedores en ejecucion
down_monitor: 
	@echo 'Contenedores en ejecucion'
	docker ps 
	$(MAKE) down_monitor_prometheus
	$(MAKE) down_monitor_grafana
	$(MAKE) down_monitor_redis
	$(MAKE) down_monitor_redis_exporter
	@echo 'Contenedores en ejecucion'
	docker ps -a


