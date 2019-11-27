# Spring-Cloud  
Tools: Eureka (C/S), 
A complete reusable Spring Cloud project, including a parent project named microservicecloud and many modules.  
* microservicecloud-api (public module): public entity  
* microservicecloud-provider-dept-8001 (submodule): service provider, port is 8001, application name: microservicecloud-dept  
* microservicecloud-consumer-dept-80 (submodule): service consumer, port is 80. Define a Javaconfig class, return RestTemplate (clent-end  restful remote access template) for use. Consumer has no service layer, so in controller, use restTemplate, postForObject, getForObject etc. to access remote service.  
* microservicecloud-eureka-7001 (submodule): Eureka server, port is 7001.  
* microservicecloud-eureka-7002 (submodule): Eureka server, port is 7002, work together with another two Eureka server as a Eureka cluster.  
* microservicecloud-eureka-7003 (submodule): Eureka server, prot is 7003, same function as above.
