# CBT025
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 025 is from Patrick Murphy of Texas Utility Services      *   FILE 025
//*           and it contains several of their TSO commands,        *   FILE 025
//*           including their CONSOLE command that has been used    *   FILE 025
//*           in production through OS/390 2.10.  This file         *   FILE 025
//*           contains the following programs:  For additional      *   FILE 025
//*           information, see the member called $DOC.              *   FILE 025
//*                                                                 *   FILE 025
//*           email:  pmurphy1@txu.com                              *   FILE 025
//*                                                                 *   FILE 025
//*           KLEENUP  -  REXX EXEC TO GENERATE HMIGRATE COMMANDS   *   FILE 025
//*                       FOR ALL BUT THE CURRENT GENERATIONS OF    *   FILE 025
//*                       THE REQUESTED DISK DATASET.               *   FILE 025
//*                                                                 *   FILE 025
//*           GETOPR  -   COMMAND FOR THE OPERATORS TO USE TO       *   FILE 025
//*                       FIND OUT THE RACF INFORMATION ASSOCIATED  *   FILE 025
//*                       WITH A GIVEN USERID AND DISPLAY IT ON THE *   FILE 025
//*                       CONSOLE.                                  *   FILE 025
//*                                                                 *   FILE 025
//*           SASSRCHD -  SAS PROGRAM THAT READS SMF DATA AT MVS    *   FILE 025
//*                       3.1.3 LEVEL AND GIVES A REPORT ON WHO     *   FILE 025
//*                       OPENED NONVSAM DATASETS, THEIR BLOCKSIZE  *   FILE 025
//*                       THAT THEY WERE OPENED WITH, AND WHO       *   FILE 025
//*                       DELETED THEM.                             *   FILE 025
//*                                                                 *   FILE 025
//*           SASSRCHV -  SAS PROGRAM THAT READS SMF DATA AT MVS    *   FILE 025
//*                       3.1.3 LEVEL AND GIVES A REPORT ON WHO     *   FILE 025
//*                       OPENED VSAM DATASETS AND WHO DELETED      *   FILE 025
//*                       THEM.                                     *   FILE 025
//*                                                                 *   FILE 025
//*           CONS390  -  CONSOLE PROGRAM MODIFIED FOR OS/390.      *   FILE 025
//*                       DISPLAYS CONSOLES AS A TSO COMMAND UNDER  *   FILE 025
//*                       ISPF OR TSO.  FEATURES:                   *   FILE 025
//*                                                                 *   FILE 025
//*                         HIGHLIGHTED MESSAGES ON CONSOLE ARE     *   FILE 025
//*                            HIGHLIGHTED                          *   FILE 025
//*                         AUTOMATIC UPDATE FEATURE                *   FILE 025
//*                         ENTER OPERATOR COMMANDS                 *   FILE 025
//*                         DISPLAY LAST IPL AND IF CLPA WAS DONE   *   FILE 025
//*                                                                 *   FILE 025
//*           CURRENT FILE IS UPDATED FOR OS/390 RELEASE 2.4.       *   FILE 025
//*           OLDER STUFF FOR ESA RELEASE 3 IS PACKAGED AS MEMBER   *   FILE 025
//*           "OLDVERS".  ESA 4.2.2 STUFF IS 2 MEMBERS:             *   FILE 025
//*           "OLDESAVR" AND "RESTESA".                             *   FILE 025
//*                                                                 *   FILE 025
//*           CONESA   -  CONSOLE PROGRAM MODIFIED FOR ESA.         *   FILE 025
//*                       DISPLAYS CONSOLES AS A TSO COMMAND UNDER  *   FILE 025
//*                       ISPF OR TSO.  FEATURES:                   *   FILE 025
//*                                                                 *   FILE 025
//*                         HIGHLIGHTED MESSAGES ON CONSOLE ARE     *   FILE 025
//*                            HIGHLIGHTED                          *   FILE 025
//*                         AUTOMATIC UPDATE FEATURE                *   FILE 025
//*                         ENTER OPERATOR COMMANDS                 *   FILE 025
//*                         DISPLAY LAST IPL AND IF CLPA WAS DONE   *   FILE 025
//*                                                                 *   FILE 025
//*           PRESENTLY WORKS UNDER OS/390 2.4 AND CORRESPONDING    *   FILE 025
//*           DFSMS.  SOME OF THE CONTROL BLOCKS THAT IT USED WERE  *   FILE 025
//*           MOVED INTO THE CONSOLE ADDRESS SPACE AFTER DFP 2.2.   *   FILE 025
//*                                                                 *   FILE 025
//*                                                                 *   FILE 025
//*           CONSOLE  -  PROGRAM TO DISPLAY CONSOLE ACTIVITY AS A  *   FILE 025
//*                       TSO COMMAND UNDER ISPF OR TSO.  FEATURES: *   FILE 025
//*                                                                 *   FILE 025
//*                         HIGHLIGHTED MESSAGES ON CONSOLE ARE     *   FILE 025
//*                             HIGHLIGHTED                         *   FILE 025
//*                         AUTOMATIC UPDATE FEATURE                *   FILE 025
//*                         ENTER OPERATOR COMMANDS                 *   FILE 025
//*                         DISPLAY LAST IPL AND IF CLPA WAS DONE   *   FILE 025
//*                                                                 *   FILE 025
//*                       PRESENTLY WORKS UNDER MVS/XA UNDER DFP    *   FILE 025
//*                       RELEASE 1 AND 2.1.                        *   FILE 025
//*                                                                 *   FILE 025
//*           MTTESA   -  USES CROSS MEMORY SERVICES TO READ AND    *   FILE 025
//*                       DISPLAY THE MASTER TRACE TABLE AS A TSO   *   FILE 025
//*                       COMMAND PROCESSOR.  THIS IS THE XA        *   FILE 025
//*                       VERSION OF THE PROGRAM THAT ORIGINATED AS *   FILE 025
//*                       MTT UNDER SP1.3.  GOOD FOR OS/390 TOO.    *   FILE 025
//*                       FEATURES:                                 *   FILE 025
//*                                                                 *   FILE 025
//*                             READ/DISPLAY MASTER TRACE TABLE     *   FILE 025
//*                             ENTER OPERATOR COMMANDS             *   FILE 025
//*                             CAN USE FIND TO SEARCH THE MASTER   *   FILE 025
//*                                 TRACE TABLE                     *   FILE 025
//*                             F 'SEARCH ARGUMENT IN QUOTES'       *   FILE 025
//*                                                                 *   FILE 025
//*             UPDATED FOR MVS/ESA 4.2.2.  OLD STUFF STILL HERE.   *   FILE 025
//*                                                                 *   FILE 025
//*           MTTXA    -  USES CROSS MEMORY SERVICES TO READ AND    *   FILE 025
//*                       DISPLAY THE MASTER TRACE TABLE AS A       *   FILE 025
//*                       TSO COMMAND PROCESSOR.  THIS IS THE XA    *   FILE 025
//*                       VERSION OF THE PROGRAM THAT ORIGINATED    *   FILE 025
//*                       AS MTT UNDER SP1.3.  FEATURES:            *   FILE 025
//*                                                                 *   FILE 025
//*                             READ/DISPLAY MASTER TRACE TABLE     *   FILE 025
//*                             ENTER OPERATOR COMMANDS             *   FILE 025
//*                             CAN USE FIND TO SEARCH THE MASTER   *   FILE 025
//*                                 TRACE TABLE                     *   FILE 025
//*                             F 'SEARCH ARGUMENT IN QUOTES'       *   FILE 025
//*                                                                 *   FILE 025
//*           MTT      -  SAME AS ABOVE FOR SP1.X SYSTEMS. WE HAVE  *   FILE 025
//*                       NOT USED FOR 3 YEARS SINCE GOING TO XA.   *   FILE 025
//*                                                                 *   FILE 025
//*           SWAPIN   -  WILL SYSEVENT A JOB TO NEW PERFORMANCE    *   FILE 025
//*                       GROUP.                                    *   FILE 025
//*                                                                 *   FILE 025
//*           AUTOWTOR -  MPF EXIT TO REPLY M.  CAN USE FOR         *   FILE 025
//*                       IEC701D WITH CARTRIDGES TO BE             *   FILE 025
//*                       INITIALIZED (THAT IS THE WAY WE USE       *   FILE 025
//*                       IT).  THE OPERATOR SETS THE MPF TO THE    *   FILE 025
//*                       PARMLIB MEMBER THAT HAS THE IEC701D       *   FILE 025
//*                       AND AUTOWTOR (SEE MPFLST03 FOR AN         *   FILE 025
//*                       EXAMPLE OF A PARMLIB MEMBER).  THE        *   FILE 025
//*                       AUTOWTOR WILL GIVE M TO THE IEC701D       *   FILE 025
//*                       AND THE OPERATOR LOOKS AT THE VISUAL      *   FILE 025
//*                       DISPLAY ON THE 3480 TO SEE WHAT           *   FILE 025
//*                       CARTRIDGE NUMBER TO INSERT.               *   FILE 025
//*                                                                 *   FILE 025
//*           IGGPRE00 -  DADSM ALLOCATION EXIT TO KEEP CERTAIN     *   FILE 025
//*                       PROBLEM DATASETS FROM BEING ALLOCATED     *   FILE 025
//*                       ON PACKS BEGINNING WITH STG (STORAGE      *   FILE 025
//*                       PACKS).                                   *   FILE 025
//*                                                                 *   FILE 025
//*           IGGPRETB -  TABLE LOADED BY IGGPRE00 THAT CONTAINS    *   FILE 025
//*                       THE FIRST 1 TO 12 CHARACTERS OF DATASET   *   FILE 025
//*                       NAMES NOT TO BE ALLOCATED ON THE PACKS    *   FILE 025
//*                       BEGINNING WITH STG.                       *   FILE 025
//*                                                                 *   FILE 025
//*           ZTPP0210 -  PROGRAM TO WRITE HEX 'FF' TO FIRST PDS    *   FILE 025
//*                       DIRECTORY ENTRY THEREBY DELETING ALL      *   FILE 025
//*                       MEMBERS OF THE PDS AND LEAVING THE        *   FILE 025
//*                       LIBRARY.                                  *   FILE 025
//*                                                                 *   FILE 025
//*           ZTPP210J -  SAMPLE EXECUTION JCL TO RUN ZTPP0210.     *   FILE 025
//*                                                                 *   FILE 025
//*           ZTPPASM  -  JCL TO ASSEMBLE ZTPP0210.                 *   FILE 025
//*                                                                 *   FILE 025
//*           SASTSOMN -  SAS PROGRAM TO PRINT TSOMON'S RECORDING   *   FILE 025
//*                       OF COMMANDS ON TSO.                       *   FILE 025
//*                                                                 *   FILE 025
//*     NOTE:  ANY MEMBERS THAT MIGHT SEEM TO BE MISSING, WILL BE   *   FILE 025
//*            FOUND IN THE OLD VERSIONS THAT ARE PACKAGED WITH     *   FILE 025
//*            THIS FILE:  SEE MEMBERS OLDVERS, OLDESAVR, RESTESA.  *   FILE 025
//*                                                                 *   FILE 025
```
