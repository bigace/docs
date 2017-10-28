# File Logger

This short tutorial will tell you how to activate File logging in BIGACE. Logging to a file  instead of database logging has the big advantage that it works even when no database connection could be established (usefull for debugging).

Please note, that the admin pnael at System/Logging will not work in combination with the FileLogger, you need to read the log files with a text editor!

Two simple steps are required:

## Activate File Logger

Read how to [configure the logger class](bigace/developer/logger).

## Reload the page

After you activated the logger, all new log entries will be written to files instead of the database. These files can be locate at **/misc/logging/**.

Take the last changed/created file and open it in a text editor to see the last written log entries.

You can delete the file, it will be recreated the next time you load the page and log entries are written.

## Logfile format

 
Logfiles have the format "system_log_" + YEAR + "_" + MONTH + "_" + DAY + ".txt"

## More about logging


*  [bigace:manual:configurations:system:logger.loglevel](bigace/manual/configurations/system/logger.loglevel)

*  [bigace:developer:logger](bigace/developer/logger)

*  [bigace:extensions:development:firephp](bigace/extensions/development/firephp)

