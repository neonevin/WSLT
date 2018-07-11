# WSLT
Documentation on WSLT - interactive mode

Invoking wslt in interactive mode 
=================================
Use java weblogic.WLST
or 
WL_HOME//oracle_common/common/bin/wlst.sh
e.g: /psoft/oracle/weblogic/wl12.2.1.3/oracle_common/common/bin/wlst.sh

Sample

[psoft@websrv1 ~]$ /psoft/oracle/weblogic/wl12.2.1.3/oracle_common/common/bin/wlst.sh
Picked up _JAVA_OPTIONS: -Djava.security.egd=file:/dev/./urandom

Initializing WebLogic Scripting Tool (WLST) ...

Welcome to WebLogic Server Administration Scripting Shell

Type help() for help on available commands

wls:/offline>

use connect () to connect to the WL server
connectconnect('username','password','t3://localhost:9200')


wls:/offline> connect('system','Sysadm123','t3://localhost:9200')
Connecting to t3://localhost:9200 with userid system ...
Successfully connected to Admin Server "PIA" that belongs to domain "psdev".

Warning: An insecure protocol was used to connect to the server.
To ensure on-the-wire security, the SSL port or Admin port should be used instead.


serverRuntime() - switches you to the runtimeMBean
Navigates to the last MBean to which you navigated in the runtime MBean hierarchy or to the root of the hierarchy, ServerRuntimeMBean. This read-only hierarchy stores the runtime MBeans that represent the server to which WLST is currently connected. In the event of an error, the command returns a WLSTException.

wls:/mydomain/serverConfig> serverRuntime()
Location changed to serverRuntime tree. This is a read-only tree with
ServerRuntimeMBean as the root.

use ls() to list the MBeans and config
Lists all the child beans and/or attributes for the current configuration or runtime bean. You can optionally control the output by specifying an argument. If no argument is specified, the command lists all child beans and attributes in the domain

wls:/psdev/serverConfig/> ls ()
dr--   AdminConsole
dr--   AppDeployments
dr--   BatchConfig
dr--   BridgeDestinations
dr--   CdiContainer
dr--   Clusters
dr--   CoherenceClusterSystemResources
....
....
-r--   AdminServerName                              PIA
-r--   AdministrationMBeanAuditingEnabled           false
-r--   AdministrationPort                           9002
-r--   AdministrationPortEnabled                    false
-r--   AdministrationProtocol                       t3s
-r--   ArchiveConfigurationCount                    0

-r-x   arePartitionsPresent                         Boolean :
-r-x   findConfigBeansWithTags                      WebLogicMBean[] : String(type),Boolean(matchAll),String[](tags)
-r-x   findConfigBeansWithTags                      WebLogicMBean[] : String(type),String[](tags)
-r-x   findPartitionByID                            WebLogicMBean : String(id)

The dr-- are the directories and -r-- are properties. -r-x are methods

Refer https://docs.oracle.com/cd/E24329_01/web.1211/e24491/nav_edit.htm#WLSTG175
