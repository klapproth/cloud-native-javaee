FROM qaware/zulu-centos-payara-micro:8u162-4.181

COPY build/postgresql/* /opt/payara/libs/
COPY build/hazelcast/* /opt/payara/libs/
COPY build/activemq/activemq-rar-5.15.3.rar /opt/payara/deployments/
COPY build/opentracing/* /opt/payara/libs/
COPY post-deploy.asadmin /opt/payara/post-deploy.asadmin

CMD ["--addjars", "/opt/payara/libs/", "--hzconfigfile", "/process-service/config/hazelcast.xml", "--postdeploycommandfile", "/opt/payara/post-deploy.asadmin", "--name", "process-service"]

COPY build/libs/process-service.war /opt/payara/deployments/
