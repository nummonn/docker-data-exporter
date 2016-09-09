#Wongnai's Relational Data Exporter in Docker

Dockerized relational data exporter from https://github.com/wongnai/relation-data-exporter

##Start a container
To start a container, just execute the following command. 
 
	docker run --rm -v /tmp:/tmp \
		wongnai/data-exporter 

The default command is to export using settings at /tmp/settings.yaml. You can mount it to different path on host.

##Overriding default command
To override the default export command, just type the command after the image name.

	docker run --rm -v /tmp:/tmp \
    		wongnai/data-exporter printConfig
    		
##Environment Variables
The default configuration assumes that mysql db is at localhost. If you want to point to remote host, change the following variables:-

* spring_datasource_url
   jdbc connection e.g. jdbc:mysql://localhost:3306/wongnai?useUnicode=true&characterEncoding=UTF-8
* spring_datasource_username
   db username
* spring_datasource_password"
	db password
    
To run a container with environment variables, execute the command:-

	docker run --rm -v /tmp:/tmp \
		-e spring_datasource_url="jdbc:mysql://myhost:3306/wongnai?useUnicode=true&characterEncoding=UTF-8" \
		-e spring_datasource_username=u \
		-e spring_datasource_password=p \
		wongnai/data-exporter 

