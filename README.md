# Oracle PDB Management Assignment

## Student Information
- **Name:** Adrien Hategekimana
- **Student ID:** 28955
- **Course:** INSY 8311 - Database Development with PL/SQL
- **Date:** February 13, 2026

---

## Overview

Hands-on Oracle Multitenant Architecture assignment demonstrating PDB creation, deletion, user management, and OEM dashboard access.

---

## Oracle Environment
- **Database:** Oracle 21c Express Edition (21.3.0.0.0)
- **OS:** Window 11
- **Tools:** SQL*Plus, Oracle Enterprise Manager

---

## Task 1: Create Main PDB

**PDB Created:** `[AD_pdb_28955]`  
**Username:** `[ADRIEN_PLSQLAUCA_28955]`

**Commands:**
```sql
CREATE PLUGGABLE DATABASE [pdb_AD_pdb_28955]
ADMIN USER [ADRIEN_PLSQL_28955] IDENTIFIED BY [12345]
FILE_NAME_CONVERT = ('pdbseed', '[pdb_AD_pdb_28955]');

ALTER PLUGGABLE DATABASE [pdb_AD_pdb_28955] OPEN;
GRANT CONNECT, RESOURCE, DBA TO [ADRIEN_PLSQL_28955];
```

**Evidence:** Screenshots show PDB creation, open state (READ WRITE), and user verification.
<img width="959" height="951" alt="PDB_Creation" src="https://github.com/user-attachments/assets/cc8ddce1-63f4-495a-8ea8-19e47782ba74" />
<img width="955" height="852" alt="PDB_Open" src="https://github.com/user-attachments/assets/5f6ee25c-0355-4c8c-9eff-bfcde40da7db" />
<img width="958" height="990" alt="USER_Exists" src="https://github.com/user-attachments/assets/f311cccf-e7bb-4d51-b1ea-fb9944aa4318" />





---

## Task 2: Create and Delete Temporary PDB

**Temp PDB:** `[AD_temp_pdb_28955]`

**Commands:**
```sql
CREATE PLUGGABLE DATABASE [AD_pdb_28955]
ADMIN USER AD_pdb_28955 IDENTIFIED BY 12345
FILE_NAME_CONVERT = ('pdbseed', '[AD_pdb_28955]');

ALTER PLUGGABLE DATABASE [AD_pdb_28955] CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE [AD_pdb_28966] INCLUDING DATAFILES;
```

**Evidence:** Screenshots show creation, both PDBs existing, deletion, and verification.
<img width="961" height="715" alt="TEMP_Creation" src="https://github.com/user-attachments/assets/4d526fbf-4962-47d1-9524-1c2cc6d71c48" />
<img width="963" height="907" alt="BOTH_PDBS" src="https://github.com/user-attachments/assets/80fe98d2-b797-4ffe-a955-0534e955224e" />
<img width="956" height="847" alt="DROP_PDB" src="https://github.com/user-attachments/assets/7f066717-63fc-4d72-9f95-4f7edfcb8b29" />
<img width="961" height="1048" alt="VERIFY_Deletion" src="https://github.com/user-attachments/assets/374d6e00-9560-4524-a94f-28b95a17c32c" />






## Task 3: Oracle Enterprise Manager

**Access:** https://localhost:5500/em (SYS as SYSDBA)

**Evidence:** OEM dashboard screenshot showing PDB status and username.
<img width="1919" height="903" alt="Oem_Dashboard" src="https://github.com/user-attachments/assets/4e3450fd-c189-4765-a1ac-fd24d4629207" />


---

## Challenges and Solutions

**Issue:** "Insufficient privileges" error when opening PDB 
<img width="962" height="661" alt="wall1" src="https://github.com/user-attachments/assets/02cd0965-c3d3-49c3-90f1-3d16ced0e527" />

**Solution:** Reconnected as SYSDBA using `sqlplus / as sysdba`
<img width="997" height="427" alt="Wall" src="https://github.com/user-attachments/assets/589da532-936d-43de-80d2-438a0b26018e" />

**Learning:** Always verify SYSDBA connection for administrative tasks





## Academic Integrity Statement

I, Adrien Hategekimana ID:28955, declare this work is completed individually. All commands, screenshots, and documentation are my own. No AI tools or collaboration were used.
