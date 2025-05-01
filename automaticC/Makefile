# ---------------------------------
# 1. Construcción de redis



# ---------------------------------
# Construir imagen de redis
# Asignar el nombre del contenedor
# Asignar un tag mediante variable

# Variables
REDIS_TAG=3
REDIS_CONTAINER_NAME=redisTest
REDIS_IMAGE_NAME=redis

build_redis:
	@echo 'Construccion de redis con el TAG=$(REDIS_TAG)'
#   Obtener la imagen  
	docker pull $(REDIS_IMAGE_NAME):$(REDIS_TAG)

#   Creacion de un contenedor
	@echo 'Correr contenedor de la imagen: $(REDIS_IMAGE_NAME)'
	docker run -d --name $(REDIS_CONTAINER_NAME) $(REDIS_IMAGE_NAME):$(REDIS_TAG)



#   ---------------------------------------
#   Mostrar las imagenenes de docker
#	Mostrar los contenedores activos
#   ---------------------------------------
show_images_containers:
	@echo 'Imagenes de docker'
	docker images
	@echo '-------------------------'  
	@echo 'Contenedores en ejecucion'
	docker ps 
	


# ------------------------------------------
# Eliminar el contenedor de redis  
#-------------------------------------------

# Eliminacion de redis
delete_redis:
	@echo 'Detener redis'
	docker stop $(REDIS_CONTAINER_NAME)
	@echo 'Eliminacion del contenedor $(REDIS_CONTAINER_NAME)'
	docker rm $(REDIS_CONTAINER_NAME)
	@echo 'Eliminacion de la imagen $(REDIS_IMAGE_NAME)'
	docker rmi $(REDIS_IMAGE_NAME):$(REDIS_TAG)
	@echo 'Imagenes de Docker:'
	docker images
	@echo 'Contenedores en ejecucion:'
	docker ps 