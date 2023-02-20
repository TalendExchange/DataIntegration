## <img src='./logo.jpg' width='40' height='40'>CofigurableJobUsingSingleton

### Overview
Problem Definition
The problem definition of the ETL job is as mentioned below.
1.\tThe Configuration values like database credentials, log file location and name needs to be kept in a XML file
a.\tName and Location of the Log File can be changed without modifying the ETL job
b.\tBy editing the configuration file, the user can change the database credentials for the source and target database.
2.\tThe ETL job must support both Windows and Unix family operation system 
3.\tValidation of configuration file needs to be done
a.\tWhether the mentioned database credentials in the configuration file is correct or not needs to be informed to the user in the log file. Even the database credentials is correct and still it is not possible to connect to a database because might be the database is down  then also the ETL job needs to log about this in the log file. 
b.\tThe log file path mentioned in the configuration file is correct or not needs to be informed to the user in the console
4.\tThe configuration file needs to be passed from command line because there are more than one instance of the job are expected to be executed at the same time. It means multiple instances of target database are having the same structure. So multiple instances of the same job having different configuration file can migrate the data from the source database in case we need to make the target database values same at the same time.  The values in the configuration files like target database name, Ip address must be different in all the configuration files.
5.\tThe command line configuration file name and location needs to be checked by the ETL job and should inform the user, in case it is wrong it must exit from the job. The ETL job can use the console to inform about the wrong command line configuration file name
6.\tThe configuration file should not be loaded each and every time from the disk whenever the values in the configuration file needs to be used by any ETL sub job. It means the configuration file should not be loaded for each sub jobs those use the content of the configuration file. The configuration file must be loaded only once and the values must be kept in the memory and to be used by all sub jobs. 
7.\tThere should be a log file and that should tell about the execution of the main job and sub jobs. 
a.\tInformation about start and end of each sub job and main job with status and time information should be kept in the log file.
b.\tIn case any record is rejected while inserting the data, it should be kept in the log file with date, time and with an error message 
c.\tNumber of records fetched from source database and number of records processed and inserted into the target database must be kept in the log file
d.\tThe log files for each instance of the job must be different and the user needs to be advised to do so. The user should not use the same log file for all the instances get executed at the same time. Other wise the log file will contain garbage 
e.\tThe ETL should manage to create log file according to date. It means the ETL will append the date value with the log file name mentioned in the configuration file.

### Images




#### Release Notes

##### 0.1 - 2009-05-11 13:56:09
The Zip file contains the following files. 

1. MDIntegrationTalendSource.zip
2. Sample ETL job.doc
3. OracleSourceTableScript.txt
4. UKConfig.xml
5. MDIntegration_0.1.zip

Execution:
==========
For execution of job use the following steps.
1)extract the contents of MDIntegration_0.1.zip to a folder.
2)Place the UKConfig.xml file in d: drive in windows.
3)Modify the database credentials for oracle(source) and MSSql(target) databases
4)Execute the oracle source database script for creating table and inserting values
5)Execute the batch file inside the MDIntegration_0.1.zip file.

After execution check the log file that you have mentioned in the UKConfig.xml file.

The windows batch file can be modified for placing the UKConfig.xml at another folder.

Importing into TOS(Talend open Studio) and modifying
====================================================

Extract the contents of MDIntegrationTalendSource.zip file into a folder and import the TOS project file into TOS.
See the provided document about the job for getting more information.

Thanks,
Pravu Mishra.

### Compatible
 -  2.3 (obsolete)