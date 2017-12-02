

1. What is ubertask optimization?

Ubertask optimization runs "sufficiently small" jobs sequentially within a single JVM. 
"Small" is defined by the 
mapreduce.job.ubertask.maxmaps, 
mapreduce.job.ubertask.maxreduces, and 
mapreduce.job.ubertask.maxbytes settings.

2. Where in CM is the Kerberos Security Realm value displayed?

CM > Settings > Kerberos > Kerberos Security Realm

3. Which CDH service(s) host a property for enabling Kerberos authentication?



4. How do you upgrade the CM agents?



5. Give the tsquery statement used to chart Hue's CPU utilization?

select cpu_system_rate where category=ROLE and serviceName="hue"

6. Name all the roles that make up the Hive service

Hive Metastore Server
WebHCat Server
HiveServer2
Gateway

7. What steps must be completed before integrating Cloudera Manager with Kerberos?

Set up a working KDC
The KDC should be configured to have non-zero ticket lifetime and renewal lifetime
OpenLdap client libraries should be installed on the CMS host
Cloudera Manager needs an account that has permissions to create other accounts in the KDC
