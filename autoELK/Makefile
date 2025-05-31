
# Comandos:   make build_containers_elk
#             make restart_alk
#             make show_elk
#	      make deep_delete

#--------------------------------------
# DEPLOY ELK
#--------------------------------------

build_elk:
	@echo 'Construccion y despliegue de ELK'
	cd elk && docker-compose build
	@echo 'Despliegue de ELK'
	cd elk && docker-compose up -d

build_containers_elk: ## Construccion de los contenedores ELK
	@echo 'Contenedores en ejecucion'
	docker ps
	$(MAKE) build_elk
	@echo 'Contenedores en ejecucion'
	docker ps 



stop_elk: ## Detiene todos los servicios ELK en ejecucion
	@echo 'Deteniendo los containers ELK'
	cd elk && docker-compose stop
	
start_elk: ## Inicia todos los servicios ELK en ejecucion
	@echo 'Iniciando los containers ELK'
	cd elk && docker-compose start

restart_elk: ## Reiniciar los containers
	@echo 'Reinicio de ELK'
	$(MAKE) stop_elk
	$(MAKE) start_elk



# Variables de las imagenes
ELASTICSEARCH=elasticsearch:7.9.2
LOGSTASH=logstash:7.9.2
KIBANA_IMAGE=kibana:7.9.2


show_elk: ## Mostrar informacion de las imagenes y contenedores activos
	@echo 'Imagenes:'
	docker images
	@echo 'Contenedores en ejecucion:'
	docker ps --filter status=running
	

deep_delete: ## Elimina los contenedores e imagenes
	$(MAKE) show_elk
	@echo 'Eliminando los containers'
	cd elk && docker-compose down
	@echo 'Eliminando las imagenes'
	docker rmi $(ELASTICSEARCH) $(LOGSTASH) $(KIBANA_IMAGE)
	$(MAKE) show_elk
