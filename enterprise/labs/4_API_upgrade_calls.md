
Latest API Version

[centos@ip-10-1-2-181 ~]$ curl -u alexpg06:cloudera 'http://localhost:7180/api/version'
v18


CM Version

[centos@ip-10-1-2-181 ~]$ curl -u alexpg06:cloudera 'http://localhost:7180/api/v18/cm/version'
{
  "version" : "5.13.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20171002-1719",
  "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
  "snapshot" : false
}


List of Users
[centos@ip-10-1-2-181 ~]$ curl -u alexpg06:cloudera 'http://localhost:7180/api/v18/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "alexpg06",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}


List of Users

[centos@ip-10-1-2-181 ~]$ curl -u alexpg06:cloudera 'http://localhost:7180/api/v18/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}