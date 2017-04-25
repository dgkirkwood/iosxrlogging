#This file is used to load our custom config for logstash as well as the grok definitions into the container each time it is built. 
#This file also instructs Logstash to launch using the supplied configuration
FROM logstash:5.2.1
RUN rm -f /usr/share/logstash/pipeline/logstash.conf
COPY logstash.conf /usr/share/logstash/config/logstash.conf
COPY grok /var/lib/logstash/etc/grok
CMD ["-f", "/usr/share/logstash/config/logstash.conf"]
