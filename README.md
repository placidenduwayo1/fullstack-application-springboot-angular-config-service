# microservices configurations centralization
This git is gathering all configuration files of utility and business microservices:
- utility microservices files:
	- ***microservices-registration-service.yml***
	- ***backend-frontend-gateway-service.yml***

- business microservices files:
	- ***clean-archi-business-service-address.yml***
	- ***clean-archi-business-service-employee.yml***
	- ***clean-archi-business-service-project.yml***
	- ***clean-archi-business-service-company.yml***

- common configirations to all utility and business microservices
	- ***application.yml***

The configurations inside each file are made for docker images related

At startup, each service contacts the configuration server and this one picks up the configuration of the service in this git.
The configuration server is as follow:
```
server:
  port: 8280
spring:
  cloud:
    config:
      server:
        git:
          uri: https://gitea.natan.fr/placidenduwayo/fullstack-application-springboot-angular-config-service.git # a git repo for all services config files
          default-label: master
```

