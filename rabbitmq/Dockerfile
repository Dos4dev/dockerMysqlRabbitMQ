FROM bijukunjummen/rabbitmq-base:3.7.0
MAINTAINER Biju Kunjummen biju.kunjummen@gmail.com

ADD rabbitmq.config /etc/rabbitmq/
ADD erlang.cookie /var/lib/rabbitmq/.erlang.cookie
ADD startrabbit.sh /opt/rabbit/

RUN chmod u+rw /etc/rabbitmq/rabbitmq.config \
&& chown rabbitmq:rabbitmq /var/lib/rabbitmq/.erlang.cookie \
&& chmod 400 /var/lib/rabbitmq/.erlang.cookie \
&& mkdir -p /opt/rabbit \
&& chmod a+x /opt/rabbit/startrabbit.sh \
&& rabbitmq-plugins enable rabbitmq_web_stomp \
&& rabbitmq-plugins enable rabbitmq_mqtt \
&& rabbitmq-plugins enable rabbitmq_tracing \
&& rabbitmq-plugins enable rabbitmq_shovel rabbitmq_shovel_management \
&& rabbitmq-plugins enable rabbitmqctl trace_on

EXPOSE 5672
EXPOSE 15672
EXPOSE 25672
EXPOSE 4369
EXPOSE 9100
EXPOSE 9101
EXPOSE 9102
EXPOSE 9103
EXPOSE 9104
EXPOSE 9105
EXPOSE 1883

CMD /opt/rabbit/startrabbit.sh
