Implemented and configured Oracle Enterprise Manager (OEM) Cloud Control 13c and installed agent on host target database using a multi-tier architecture, separating the OEM Server (OMS) and the Management Repository (OMR). OEM serves as a centralized GUI console for DBAs to monitor, schedule, and execute jobs across multiple databases from a single point of control.


Prerequirements:
- A dedicated server for OEM Cloud Control (OMS) installation.
- A separate server for the Oracle Management Repository (OMR) database. Single server for database management repository OEM
- Agent host for add and monitor database target






1. Verified the Linux version to ensure compatibility with the Oracle Database 19c pre-installation requirements

   <img width="530" height="447" alt="Screenshot (1468)" src="https://github.com/user-attachments/assets/16d49ab5-8ca1-4006-b81b-589c58c1620f" />


2. Installed the oracle-database-preinstall-19c package using yum to automate kernel and user configurations

   <img width="893" height="803" alt="Screenshot (1478)" src="https://github.com/user-attachments/assets/59b21524-afb6-4d63-b272-82ea559f615c" />


3. Verified sysctl kernel parameters to ensure compliance with official Oracle standards

   <img width="409" height="319" alt="Screenshot (1470)" src="https://github.com/user-attachments/assets/42e92db5-e5b3-4c5d-bea5-0939b6a04cb2" />


4. Confirmed the existence and correct configuration of the oracle user ID and associated OS roles

   <img width="379" height="222" alt="Screenshot (1471)" src="https://github.com/user-attachments/assets/19aa1bf7-71a0-4b4f-b82d-fdd131bf1f64" />


5. Created a secure password for the oracle user to protect system accessibility

   <img width="890" height="78" alt="Screenshot (1472)" src="https://github.com/user-attachments/assets/a4beb5d5-a90a-457d-9c7d-5a1940efdbc6" />


6. Created physical directory paths to store logs and binaries for both the Oracle Management Server (OMS) and Management Agent

   <img width="892" height="163" alt="Screenshot (1474)" src="https://github.com/user-attachments/assets/c2c72de6-d67b-4e71-9363-4e59d4abfcb0" />


7. Disabled firewalld and selinux on both the OEM and Repository servers to allow seamless communication between the nodes

   <img width="893" height="407" alt="Screenshot (1475)" src="https://github.com/user-attachments/assets/cb098cd9-198a-459a-a311-b766138898d5" />
   <img width="877" height="290" alt="Screenshot (1476)" src="https://github.com/user-attachments/assets/68b69882-4622-4ef6-858c-09c8e50ba1db" />


8. Configured the .bash_profile for the oracle user to automate the setting of environment variables and home paths

   <img width="687" height="491" alt="Screenshot (1483)" src="https://github.com/user-attachments/assets/eb212c0b-7067-4382-a008-fab1a2ed369f" />


9. Downloaded the OEM installation binaries from the official Oracle website

   <img width="1816" height="950" alt="Screenshot (1485)" src="https://github.com/user-attachments/assets/57089e41-4a15-427c-8b78-a44358ec71b6" />


10. Mounted the downloaded software to the Linux OS using VMware Shared Folders

    <img width="786" height="253" alt="Screenshot (1486)" src="https://github.com/user-attachments/assets/c0b551ba-24d0-495e-81d5-ce2c184c9e30" />


11. Copied all OEM installation files from the mount point to the local directory

    <img width="889" height="271" alt="Screenshot (1487)" src="https://github.com/user-attachments/assets/6d357c56-19cb-41a6-a8b5-38045bf454bb" />


12. Verified the Repository database was running on a separate server to eliminate a Single Point of Failure

    <img width="705" height="102" alt="Screenshot (1497)" src="https://github.com/user-attachments/assets/56261c6c-5670-46af-a5cb-b2d36ff1f040" />
    <img width="672" height="360" alt="Screenshot (1499)" src="https://github.com/user-attachments/assets/998739e5-72af-414c-a08e-afb5460627a3" />
    <img width="892" height="789" alt="Screenshot (1500)" src="https://github.com/user-attachments/assets/d3f9b75a-dcca-4ef0-b5a5-eb6bf044c5db" />


13. Added the IP addresses and hostnames of both servers to /etc/hosts to establish network resolution

    <img width="891" height="382" alt="Screenshot (1503)" src="https://github.com/user-attachments/assets/becb2581-17ed-4021-a0bf-80d3c34a06d8" />
    <img width="872" height="354" alt="Screenshot (1504)" src="https://github.com/user-attachments/assets/2b84dc50-09dc-4937-9326-358a6aefcb42" />

    
14. Configured specific database parameters on the repository instance to meet the minimum mandatory requirements of the OEM server

    <img width="740" height="757" alt="Screenshot (1498)" src="https://github.com/user-attachments/assets/b795152d-b1c3-416a-8aef-c223871f1045" />


15. Performed the OEM installation and configuration via the GUI by executing the em13500_linux64.bin installer

    <img width="893" height="145" alt="Screenshot (1505)" src="https://github.com/user-attachments/assets/7b5b546c-679b-4175-bccb-235212aa8f56" />
    <img width="992" height="787" alt="Screenshot (1506)" src="https://github.com/user-attachments/assets/d79ebf06-32b5-4172-be38-6452cb48b180" />
    <img width="996" height="776" alt="Screenshot (1507)" src="https://github.com/user-attachments/assets/20ac2700-8d4a-4ea3-9285-c8f15ad1dac6" />
    <img width="1001" height="780" alt="Screenshot (1508)" src="https://github.com/user-attachments/assets/36a65fe4-8afd-4955-8e99-8f6a8bc565a1" />
    <img width="994" height="778" alt="Screenshot (1509)" src="https://github.com/user-attachments/assets/3396516a-0a7c-43ac-86bd-4517a3be1d43" />
    <img width="996" height="783" alt="Screenshot (1510)" src="https://github.com/user-attachments/assets/8ceb0b3c-6535-4546-872f-fcba4c1e21eb" />
    <img width="998" height="785" alt="Screenshot (1511)" src="https://github.com/user-attachments/assets/1617893b-9404-48e2-81c5-73e3f55021d4" />
    <img width="988" height="773" alt="Screenshot (1512)" src="https://github.com/user-attachments/assets/722a88b7-d822-4160-be6f-a9ddd1dcb232" />
    <img width="1006" height="787" alt="Screenshot (1513)" src="https://github.com/user-attachments/assets/b78b2cb8-3fd8-4b3c-974e-ede59db7593a" />
    <img width="998" height="782" alt="Screenshot (1515)" src="https://github.com/user-attachments/assets/a242e174-6c04-4f7e-9f1c-662d88a27523" />
    <img width="987" height="793" alt="Screenshot (1517)" src="https://github.com/user-attachments/assets/19cb6479-8c39-457f-8676-f1ad35076211" />
    <img width="986" height="780" alt="Screenshot (1518)" src="https://github.com/user-attachments/assets/bc31db46-e948-49af-9fdb-b02cc8198964" />
    <img width="991" height="790" alt="Screenshot (1520)" src="https://github.com/user-attachments/assets/e2585a33-3e29-4a06-8446-b4573e47df58" />
    <img width="999" height="785" alt="Screenshot (1521)" src="https://github.com/user-attachments/assets/29ea5f8d-07fb-48df-9f7d-0892ffd95ac2" />
    <img width="984" height="782" alt="Screenshot (1522)" src="https://github.com/user-attachments/assets/818f1255-4f9c-469c-b316-60cc6a18c480" />
    <img width="994" height="795" alt="Screenshot (1523)" src="https://github.com/user-attachments/assets/3f1a250f-6383-4cbf-bb38-7ea13b4daceb" />


16. Confirmed that the Oracle Management Server (OMS) and Management Agent were running successfully on the OEM server

    <img width="794" height="789" alt="Screenshot (1526)" src="https://github.com/user-attachments/assets/c8170888-c5c4-4df3-a596-f2ae0fd6d80c" />
    <img width="794" height="789" alt="Screenshot (1526)" src="https://github.com/user-attachments/assets/1c47ea10-6294-47cb-bb97-0bcc00259adb" />


17. Accessed the OEM console URL via a web browser and logged in using the SYSMAN superuser account

    <img width="1593" height="1038" alt="Screenshot (1528)" src="https://github.com/user-attachments/assets/a8320969-a870-4800-8dc1-cb732970e79f" />


18. Accepted the initial configuration rules to access the main OEM dashboard

    <img width="1920" height="1028" alt="Screenshot (1529)" src="https://github.com/user-attachments/assets/b5e3d83e-d33f-45d4-b230-09222b990d45" />
    <img width="1920" height="1028" alt="Screenshot (1530)" src="https://github.com/user-attachments/assets/a019a1fd-09c7-4135-9b55-f15ce449a318" />


19. Navigated to the "Add Targets Manually" feature to initiate the Management Agent installation on the target host

    <img width="1920" height="1022" alt="Screenshot (1555)" src="https://github.com/user-attachments/assets/6a411870-3d36-4043-8005-c887b5be706c" />


20. Selected the "Install Agent on Host" option to deploy the monitoring agent to the remote database server

    <img width="1920" height="1031" alt="Screenshot (1557)" src="https://github.com/user-attachments/assets/67b41a7f-a474-4be8-a8de-9d6ee4c18a11" />


21. Added the target hostname and operating system platform to establish connectivity between the OMS and the target database server

    <img width="1920" height="1031" alt="Screenshot (1557)" src="https://github.com/user-attachments/assets/8d2c8168-40af-4520-95d1-4888738e2865" />


22. Inputed the required configuration details, ensuring the installation directory was correctly specified and created at the OS level to store agent binaries and logs

    <img width="1920" height="1016" alt="Screenshot (1558)" src="https://github.com/user-attachments/assets/02bf4fcb-cd95-48be-9bc8-87696bf36ca3" />


23. Executed the deployment process and verified the agent was installed on the target host successfully without any errors

    <img width="1920" height="1016" alt="Screenshot (1559)" src="https://github.com/user-attachments/assets/1c891b9d-c3d6-414d-9812-bca1a0441b51" />
    <img width="1920" height="1024" alt="Screenshot (1560)" src="https://github.com/user-attachments/assets/3c12cc63-d80a-416f-80b4-e9604d67e60e" />


24. Validated the host status in the OEM dashboard to ensure the new target server was "Up" and health

    <img width="1920" height="1034" alt="Screenshot (1561)" src="https://github.com/user-attachments/assets/857eeb7b-aa30-4fb3-bd68-71ef0ead79a8" />
    <img width="1920" height="1031" alt="Screenshot (1562)" src="https://github.com/user-attachments/assets/762815be-b93f-4053-b6d2-bc24c696b5fe" />


25. Initiated the configuration for the specific database target to enable monitoring within the OEM console

    <img width="1920" height="1025" alt="Screenshot (1567)" src="https://github.com/user-attachments/assets/efbae9d7-aa64-4399-bc1f-3a307ce57442" />
    <img width="1920" height="1031" alt="Screenshot (1568)" src="https://github.com/user-attachments/assets/63277dd1-0f59-4682-bf50-4236543f5758" />


26. Identified and added the specific database instance from the host server to be managed by OEM

    <img width="1920" height="1028" alt="Screenshot (1569)" src="https://github.com/user-attachments/assets/b49ebcdb-db23-4640-b1fc-a3512e0897e4" />


27. Configured the discovery settings for the Database, ASM, and Listener. Provided the credentials (SYSMAN or SYSDBA) to authorize monitoring

    <img width="1920" height="1031" alt="Screenshot (1570)" src="https://github.com/user-attachments/assets/1e5f764b-111e-45ec-92e7-1b636e561cb2" />


28. Confirmed the configuration was successful and verified the database instance was now listed as a managed target

    <img width="1920" height="1038" alt="Screenshot (1572)" src="https://github.com/user-attachments/assets/a4735ac0-9887-4e42-94e2-dabc42bde856" />
    <img width="1920" height="1031" alt="Screenshot (1573)" src="https://github.com/user-attachments/assets/f31a09f2-efd2-4521-950f-0948a0305c72" />


29. Accessed the main OEM monitoring dashboard to view the real-time health and anything of the database instance

    <img width="1920" height="1034" alt="Screenshot (1574)" src="https://github.com/user-attachments/assets/3a0956da-e22c-4bc9-8fb2-316bac9c93fa" />
    <img width="1920" height="1028" alt="Screenshot (1575)" src="https://github.com/user-attachments/assets/9c21827e-d330-4c36-ace4-7b1b95a03ba3" />



    































 





    
















