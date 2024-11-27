1. Create an account with Oracle and Login
2. Goto the oracle container registry: https://container-registry.oracle.com/ords/f?p=113:10::::::
3 Goto oracle enterprise version  21.3.0.0: https://container-registry.oracle.com/ords/f?p=113:4:108657991767292:::4:P4_REPOSITORY,AI_REPOSITORY,AI_REPOSITORY_NAME,P4_REPOSITORY_NAME,P4_EULA_ID,P4_BUSINESS_AREA_ID:9,9,Oracle%20Database%20Enterprise%20Edition,Oracle%20Database%20Enterprise%20Edition,1,0&cs=3DOOKjgd3JE4Fs_6wh-bZySP0FrDN-O5iQXjDUHsKjV0L5x7s9yniBlj3d8MBt2AhVYUl9cL-3DU829RsmQf1sA
4. Sign in and agree to the farking stupid terms and agreement.
5. Login to the oracle repository using your oracle login.
    ``` 
    docker login container-registry.oracle.com
    ``` 
6. Get the latest Oracle db image (23 at time of writting)
    ``` 
    docker pull container-registry.oracle.com/database/enterprise:latest
    ``` 
7. Run above image in a container
    ``` 
    docker run -d -p 1521:1521 --name {My-Container-Name} -e ORACLE_PWD={SYS-USER-PASSWORD} -e ORACLE_SID={Oracle-SID} --shm-size="8g" container-registry.oracle.com/database/enterprise
    ```
8. Connect to db using Oracle Sql Developer:
    ```Uesrname: SYS
    Role: SYSDBA
    Password: in Run command above
    Hostname: localhost
    port: 1521
    SID: in Run Command above
    ```
