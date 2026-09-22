# Oracle PDB Management - Assignment II (INSY 8311)

**Name:** Ikuzwe Shema Elie

**Student ID:** 28924

**Group:** C

**Course:** Database Development with PL/SQL (INSY 8311)

**Instructor:** Eric Maniraguha

**Oracle Environment:** Oracle XE via Docker on Linux (CDB: XE/FREE - version 23)
**Repo name:** `oracle_pdb_ass_II_28924_ikuzwe`

## Overview of Tasks

1. Task 1: Create a new Pluggable Database (PDB) + create user inside PDB for future class work.
2. Task 2: Create a temporary PDB, verify it exists, delete it completely, confirm gone.
3. Task 3: Access Oracle Enterprise Manager (OEM) dashboard showing environment + PDBs.
4. Task 4: Document all work professionally on public GitHub with screenshots.

## Oracle Environment Used

* Host OS: Linux (Ubuntu - update version)
* Oracle in Docker: `gvenzl/oracle-xe` - update exact image/tag
* Container name: `oracle-xe` - update to yours
* CDB Name: `XE` - update to yours (XE or FREE)
* Connection: SYS AS SYSDBA to CDB root, then ALTER SESSION SET CONTAINER
* OEM URL: https://localhost:5500/em

## Task Explanations

### Task 1: Create New PDB
* PDB Name: `ik_pdb_28924`
* Username inside PDB: `ikuzwe_plsqlauca_28924`
* Steps done:
  1. Connected to CDB root as SYSDBA, checked `SHOW PDBS;`
  2. Created PDB from SEED, opened it READ WRITE, saved state.
  3. Switched to PDB, created user, granted CONNECT, RESOURCE, verified in DBA_USERS.
* Evidence: `screenshots/pdb_creation/`

### Task 2: Create and Delete PDB
* Temp PDB Name: `ik_to_delete_pdb_28924`
* Steps done:
  1. Created temp PDB from SEED, verified with `SHOW PDBS;`
  2. Closed PDB, dropped with INCLUDING DATAFILES, verified gone with `SHOW PDBS;`
* Evidence: `screenshots/pdb_deletion/`

### Task 3: OEM Setup
* Accessed OEM at `https://localhost:5500/em`, logged in, dashboard shows CDB + PDBs.
* Username visible on dashboard top-right.
* Evidence: `screenshots/oem_dashboard/`

## Queries / Commands Log
<!-- Paste YOUR OWN typed queries here after you run them in Docker -->

```sql
-- 1. Check existing PDBs
SHOW PDBS;

-- 2. Task 1: paste your CREATE PLUGGABLE DATABASE ... here
-- 3. Task 1: paste your ALTER PLUGGABLE DATABASE ... OPEN here
-- 4. Task 1: paste your CREATE USER ... here

-- 5. Task 2: paste your temp PDB create / drop here
```

## Results / Screenshots

* `screenshots/pdb_creation/01_pdb_create.png` - creation command + result
* `screenshots/pdb_creation/02_pdb_open.png` - open state
* `screenshots/pdb_creation/03_user_created.png` - username visible
* `screenshots/pdb_deletion/01_temp_create.png`
* `screenshots/pdb_deletion/02_temp_drop.png`
* `screenshots/oem_dashboard/01_oem.png`

## Challenges Faced

* Challenge 1: Docker port 5500 not mapped / PDB in MOUNTED state - Resolution: TBD by student
* Challenge 2: ORA-65096 invalid common user - Resolution: switched container with ALTER SESSION SET CONTAINER
* Update with your real issues or write: No major issues encountered.

## Integrity Statement
I, Ikuzwe Shema Elie (28924), declare this work is my own individual execution and documentation. No copying from classmates, no shared screenshots/repos, no AI-generated commands. All screenshots are from my own Docker Oracle environment.

## Submission Details Block

```
Repository Link: https://github.com/shemaikuzwe/oracle_pdb_ass_II_28924_ikuzwe
PDB Name Created: ik_pdb_28924
Issues Encountered: No
```

## How to Reproduce
1. Start Docker Oracle container
2. Connect as SYSDBA, run queries from Queries section above
3. Open OEM URL to verify
