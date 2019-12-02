# Spring-Cloud  
Tools: Eureka (C/S), Ribbon (client-end load balancer, RoundRobinRule, RandomRule, RetryRule, self-defined rule), Feign (make writing web service client easier), Hystrix (fault tolerance), Zuul (routing, filter), config server.        
A complete reusable Spring Cloud project, including a parent project named microservicecloud and many modules.  
* microservicecloud-api (public module): public entity  
* microservicecloud-provider-dept-8001 (submodule): service provider, port is 8001, application name: microservicecloud-dept, independent database.      
* microservicecloud-consumer-dept-80 (submodule): service consumer, port is 80. Define a Javaconfig class, return RestTemplate (clent-end  restful remote access template) for use. Consumer has no service layer, so in controller, use restTemplate, postForObject, getForObject etc. to access remote service.  
* microservicecloud-eureka-7001 (submodule): Eureka server, port is 7001.  
* microservicecloud-eureka-7002 (submodule): Eureka server, port is 7002, work together with another two Eureka server as a Eureka cluster.  
* microservicecloud-eureka-7003 (submodule): Eureka server, prot is 7003, same function as above.
* microservicecloud-provider-dept-8002 (submodule): service provider, port is 8002, application name: microservicecloud-dept, independent database.      
* microservicecloud-provider-dept-8003 (submodule): service provider, port is 8003, application name: microservicecloud-dept, independent database.    
* microservicecloud-consumer-dept-feign (submodule): service consumer based on Feign, port is 80, interface-based development, add service interface define in  microservicecloud-api (public module). Feign integrates Ribbon for load balance.  
* microservicecloud-provider-dept-hystrix-8001 (submodule): service provider with Hystrix, port is 8001, define fallbackMethod for circuit breaker (in provider), define fallbackFactory for degradation (in consumer, in microservicecloud-api, identify that the service is not available at that time).      
* microservicecloud-consumer-hystrix-dashboard (submodule): visual interface for service access, port is 9001.  
* microservicecloud-zuul-gateway-9527 (submodule): gateway service provider, registered in Eureka as a microservice, port is 9527.  
* microservicecloud-config-3344 (submodule): config server, port is 3344, connect with local git repository and remote repository to share dynamic configuration.  
* microservicecloud-config-3355 (submodule): config client, port is 3355, define bootstrap.yml to track config server 3344, then get git address, then get client config.
### Test on single machine, need to change system hosts file. C:\Windows\System32\drivers\etc, add below contents:  
127.0.0.1	eureka7001.com  
127.0.0.1	eureka7002.com  
127.0.0.1	eureka7003.com  
127.0.0.1	myzuul.com  
127.0.0.1	config-3344.com  
127.0.0.1	client-config.com  
