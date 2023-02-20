# pravu
  <nospam+freemailid@yahoo.com>

## <a href='./components/CofigurableJobUsingSingleton/readme.md'><img src='./components/CofigurableJobUsingSingleton/logo.jpg' width='40' height='40'> CofigurableJobUsingSingleton</a>
 :warning: Compatibility not known

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

<img src='./components/CofigurableJobUsingSingleton/sample.jpg'>

## <a href='./components/TimeDimensionGenerator/readme.md'><img src='./components/TimeDimensionGenerator/logo.jpg' width='40' height='40'> TimeDimensionGenerator</a>
 :warning: Compatibility not known

A datamart or data warehouse usually need a time dimension to use for date queries that look at periods, weeks, months, etc. There are multiple different ways to generate and keep rows in Time Dimension table and here is one of those ways and by using Talend 3.1.  

This ETL job is been developed by using Talend 3.1.

 For more information please read the document provided in the zip file.

The zip file contains the following
1) A zip file that that has the Talend 3.1 project
2) TimeDimension Document
3) ReadMe file

Thanks,
Pravu Mishra

<img src='./components/TimeDimensionGenerator/sample.jpg'>
