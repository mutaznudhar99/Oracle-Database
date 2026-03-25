Implemented data migration on an Oracle standadlone 12c to 19c server accross different server using DataPump. DataPump tasks as a saving DML processing like Insert, Update, and Delete. This method important to switch data to another version zero downtime. 



1. Create directory to saving datapump on the primary instance

   <img width="633" height="60" alt="Screenshot (1400)" src="https://github.com/user-attachments/assets/325dd0fc-0fbf-467c-99b8-d3d762d83fbf" />


2. Create extension directory datapump inside database instance using sqlplus and gave permission directory datapump using grant to user take backup

   <img width="774" height="365" alt="Screenshot (1401)" src="https://github.com/user-attachments/assets/60bcdb9b-dd68-4468-8886-9ffc0a1e3497" />


3. Validate data inside 12c database as a real workload to migration to 19c database in another server
   
   <img width="780" height="528" alt="Screenshot (1402)" src="https://github.com/user-attachments/assets/6197b9a4-9e7d-4e46-b60f-22ca777fac30" />


4. Execute expdpd to export datapump on inside 12c database to directory datapump

   <img width="866" height="610" alt="Screenshot (1403)" src="https://github.com/user-attachments/assets/f1d80450-62cf-4978-93cc-49e460bf36c4" />


5. Verified exists datapump file on directory datapump to ensure all file has exist

   <img width="622" height="127" alt="Screenshot (1404)" src="https://github.com/user-attachments/assets/16ba0acb-dd5a-4fbd-b4cc-659a75c307fb" />


6. Create directory datapump on server 19c database to saving datapumo from 12c database

   <img width="630" height="65" alt="Screenshot (1405)" src="https://github.com/user-attachments/assets/b54cec23-314b-43a9-9b37-10515afb6720" />


7. Transfer directory datapump from 12c database server to 19c database server using protocol scp

   <img width="880" height="348" alt="Screenshot (1406)" src="https://github.com/user-attachments/assets/8ba6536d-ef4b-49f4-9d0b-562c637f7910" />


8. Verified directory datapump to ensure all file datapump has identic with primary database

   <img width="624" height="128" alt="Screenshot (1407)" src="https://github.com/user-attachments/assets/9e3617fe-876b-481f-835a-30ded01e599a" />


9. Create extension directory datapump inside 19c database instance using sqlplus to reading directory datapump before import data inside database instance

   <img width="721" height="388" alt="Screenshot (1409)" src="https://github.com/user-attachments/assets/6e5c3bcf-577b-4f0f-8322-1395d81b8eaf" />


10. Execute impdp on OS level to import datapump from directory to inside 19c database instance

    <img width="721" height="388" alt="Screenshot (1409)" src="https://github.com/user-attachments/assets/2cd94174-4198-4f39-86c1-5f28d674f329" />


11. Validate data stay exist to ensure zero data loss and consistency data from 12c database server to 19c database server

    <img width="738" height="576" alt="Screenshot (1411)" src="https://github.com/user-attachments/assets/7924cf10-4ea4-46a1-b971-21cf21c4d148" />















