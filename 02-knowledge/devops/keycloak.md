---
tags:
  - area/devops
  - area/knowledge
  - topic/aws
  - topic/database
  - topic/docker
  - topic/kubernetes
  - topic/snippets
  - topic/testing
---

# Keycloak

Downloaded Zip of Keycloak 11.0.2 - https://www.keycloak.org/archive/downloads-11.0.2.html
Exported TXAI realm from our docker keycloak - txai.json
Imported it into the Zip of Keycloak
(Had issues with the themes) Copied over the themes
Download a JDBC postgres driver and setup the database configuration profile for it

Edit the  section of standalone/configuration/standalone.xml 

### Creating Keycloak TXAI distribution

#### Downloaded Zip of Keycloak (Current used version 11.0.2)
Keycloak 11.0.2 - https://www.keycloak.org/archive/downloads-11.0.2.html

#### Export TXAI realm from our docker keycloak TXAI
Start up latest version of keycloak txai image 
Run commands to create a json file of txai realm:

`docker exec -it \[CONTAINER_ID\] bin/sh`
`cd opt/jboss/keycloak/bin/`
`./standalone.sh -Dkeycloak.migration.action=export -Dkeycloak.migration.provider=singleFile -Djboss.socket.binding.port-offset=100 -Dkeycloak.migration.realmName=txai -Dkeycloak.migration.file=/tmp/txai_realm.json`

Copy txai realm json file to local directory:
`docker cp \[CONTAINER_ID\]:/tmp/txai_realm.json \[LOCAL_PATH\]`

#### Add TXAI theme
Copy the TXAI theme folders from server repository
`server/keycloak/themes/` to `keycloak-11.0.2/themes`

#### Setup JDBC driver
Follow steps on downloading a JDBC driver for your chosen database and updating the datasource configuration. 
https://www.keycloak.org/docs/latest/server_installation/#_database

NOTE: Connect to the chosen database before importing the TXAI realm

#### Keycloak TXAI distribution Zip
Download Keycloak txai distribution:
https://nexus.live.logicalglue.net/#browse/browse:raw:lg%2Fkeycloak%2Fkeycloak-txai-1.0.6.zip

#### Postgres Database Configuration
Modified the `` configuration inside the `standalone.xml` found inside
`keycloak-txai-1.0.6/standalone/configuration`
{F26230}
Edit the `connection-url`, `user-name` and `password` to connect to your postgres database.

 
#### Running Keycloak
To start keycloak server:
`./keycloak-txai-1.0.6/bin/standalone.sh`

#### Import TXAI realm
Download TXAI realm file - txai_realm.json - https://nexus.live.logicalglue.net/#browse/browse:raw:lg%2Fkeycloak%2Ftxai_realm.json

Navigate to keycloak admin console - `localhost:8080/auth/`
Login to the Keycloak admin console and hover over "Master" realm name on the top left-hand side.
{F26244}
Click `Add realm` and select the txai_realm.json file to import.

#### Setup LDAP and Active Directory
Keycloak can work along side external user databases
On the User Federation page we are able to select a LDAP protocol connection.
{F26246}

##### Provider Settings:
Enter your provider settings to connect with the directory server:

`Console Display Name` - Display name of provider 
`Edit Mode` - READ_ONLY
`Import Users` - ON
`Vendor` - Select the type of directory server
Default LDAP attributes (Username, RDN, etc) are autofilled based on the directory server selected. Modify the values if needed to match you directory server
`Connection URL` - LDAP connection URL 
Click the **Test Connection** button to see if Keycloak is able to connect to the directory server 
`Users DN` - Distinguished name of LDAP Tree where the users are located.
`Bind DN` - Distinguished name of LDAP admin, used by Keycloak to access LDAP server 
`Bind Credential` - Password of LDAP admin
Click **Test Authentication** button to ensure that LDAP authentication works.
Finally click the `Save button

##### Import Users
To import the users into the Keycloak database. Click the `Synchronise all users` button on your User Federation provider
Go to Users page and click `View all Users`
You should now see all the users imported
You can now assign groups/roles to each user.

For more information in Group creation and assignment -> https://phabricator.live.logicalglue.net/w/developers/keycloak/

## Related
- [[devops-moc]]
- [[helm-keycloak]]
- [[cloudwatch]]
- [[vpc-lab]]
