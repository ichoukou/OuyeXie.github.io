# TAS

 - [SetupProject](https://w.888.com/bin/view/ELM/YVR-ELM/SetupProject/)
 
# General Command 

 - brazil-build
 - brazil-build server
 - brazil workspace --sync //Syncing (aka updating) your client
 - brazil workspace --dryrun //Brazil can submit a dry-run build request in PackageBuilder for all the code in your 
 workspace (even if it hasn't been committed yet). This is useful to verify that your build doesn't depend on 
 anything special on your desktop. Note that this command will package up build artifacts (such as .pyc files) as 
 well as source files, so you might want to remove them before submitting.