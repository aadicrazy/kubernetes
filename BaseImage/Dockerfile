FROM amazonlinux:2
COPY splunkforwarder-6.0.2-196940-linux-2.6-x86_64.rpm /opt
#RUN yum install -y tar && \
#    yum update -y && yum -y install shadow-utils.x86_64 wget && \
#    groupadd --system ${SPLUNK_GROUP} && \
#    useradd --system -g ${SPLUNK_GROUP} ${SPLUNK_USER} && \
#    rpm -ihv /opt/splunkforwarder-6.0.2-196940-linux-2.6-x86_64.rpm
#RUN /opt/splunkforwarder/bin/splunk start
RUN yum install shadow-utils net-tools procps which hostname -y && \
	groupadd --system splunk && useradd --system -g splunk splunk
RUN rpm -i /opt/splunkforwarder-6.0.2-196940-linux-2.6-x86_64.rpm --nodeps && \
	rm -rf /opt/splunkforwarder-6.0.2-196940-linux-2.6-x86_64.rpm
RUN /opt/splunkforwarder/bin/splunk start --accept-license --answer-yes --no-prompt
#ENTRYPOINT ["/sbin/entrypoint.sh"]
CMD ["/bin/bash"]
