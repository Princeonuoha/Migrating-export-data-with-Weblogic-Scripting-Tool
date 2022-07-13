# Migrating-export-data-with-Weblogic-Scripting-Tool

This file helps you migrate user and roles using the weblogic scripting tool..Follow the steps and it should work for you.



1. Open weblogic scripting tool in the middleware ORACLE_HOME:/u01/app/oracle/product/ORACLE_HOME/oracle_common/common/bin

and run the command ./wlst.sh

2. The scripting tool starts, but it is offline....so first, run the command below:

connect('weblogic','magnus20c','t3://eposbi:9500/console')

3. run the command below
      domainRuntime()

4. cd('/DomainServices/DomainRuntimeService/DomainConfiguration/bi/SecurityConfiguration/bi/DefaultRealm/myrealm/AuthenticationProviders/DefaultAuthenticator')


note: bi is the name of domain and occurs in two different places on the script....change bi to the name of your domain

5. Finally to export the data, run the  following

cmo.exportData('DefaultAtn','/u01/app/oracle/product/ORACLE_HOME/WLSrealmscripttotest', Properties())

note: '/u01/app/oracle/product/ORACLE_HOME/WLSrealmscripttotest' is my desired location where the file should be saved. WLSrealmscripttotest is a folder name that does not exist before running the script..I just created the name so WLST knows where to save 
