implemented data migration from a standalone Oracle 12c server to a 19c server using Oracle Data Pump. This method is essential for moving data across different versions while ensuring data consistency and minimizing downtime.



1. Created a physical folder on the Primary (12c) server to store the Data Pump export files

   <img width="633" height="60" alt="Screenshot (1400)" src="https://github.com/user-attachments/assets/325dd0fc-0fbf-467c-99b8-d3d762d83fbf" />


2. Created a directory object inside the database using SQL*Plus. Then, grant READ and WRITE permissions to the user performing the backup

   <img width="774" height="365" alt="Screenshot (1401)" src="https://github.com/user-attachments/assets/60bcdb9b-dd68-4468-8886-9ffc0a1e3497" />


3. Verified the data inside the 12c database before migration. This acts as a baseline to ensure data consistency after the move
   
   <img width="780" height="528" alt="Screenshot (1402)" src="https://github.com/user-attachments/assets/6197b9a4-9e7d-4e46-b60f-22ca777fac30" />


4. Ran the expdp utility at the OS level to export the 12c database schemas/data into the Data Pump directory

   <img width="866" height="610" alt="Screenshot (1403)" src="https://github.com/user-attachments/assets/f1d80450-62cf-4978-93cc-49e460bf36c4" />


5. Verified the physical directory to ensure that the dump file (.dmp) and log file (.log) were created successfully

   <img width="622" height="127" alt="Screenshot (1404)" src="https://github.com/user-attachments/assets/16ba0acb-dd5a-4fbd-b4cc-659a75c307fb" />


6. create a physical directory where the transferred Data Pump files will be saved on the new 19c server

   <img width="630" height="65" alt="Screenshot (1405)" src="https://github.com/user-attachments/assets/b54cec23-314b-43a9-9b37-10515afb6720" />


7. transfer the export files from the 12c server to the 19c server using the Secure Copy Protocol (scp)

   <img width="880" height="348" alt="Screenshot (1406)" src="https://github.com/user-attachments/assets/8ba6536d-ef4b-49f4-9d0b-562c637f7910" />


8. Confirmed all files transferred to the 19c server are identical in size and name to the source files
   
   <img width="624" height="128" alt="Screenshot (1407)" src="https://github.com/user-attachments/assets/9e3617fe-876b-481f-835a-30ded01e599a" />


9. created the directory object pointing Inside the 19c database to the transfer folder so the database can read the dump files

   <img width="721" height="388" alt="Screenshot (1409)" src="https://github.com/user-attachments/assets/6e5c3bcf-577b-4f0f-8322-1395d81b8eaf" />


10. Ran the impdp utility at the OS level on the 19c server to import the data into the new database instance

    <img width="721" height="388" alt="Screenshot (1409)" src="https://github.com/user-attachments/assets/2cd94174-4198-4f39-86c1-5f28d674f329" />


11. Final data validation to ensure zero data loss and successful migration

    <img width="738" height="576" alt="Screenshot (1411)" src="https://github.com/user-attachments/assets/7924cf10-4ea4-46a1-b971-21cf21c4d148" />















