# Files / Directories and Data Manupulation

Learn more about files manipulation, default hosting directory structure, permission settings and more.

## Default Hosting Directories Stucture

Default directory stucture for every web hosting is:

 - **web** - the directory where your website files are located. Upload your public website files to this directory.
 - **log** - webserver access logs and php error logs are placed to this directory. Logs are rotating.
 - **private** - used for user files that should not be accessible from the Web (publicly)
 - **tmp** - directory for your temporary files like PHP sessions, PHP uploads etc.

Optional directories which may be present:

```.ssh, bin, dev, etc, lib, lib64, usr, var, ssl, cgi-bin, webdav```

Those are system directories that you do not need to change, edit, or access. You have limited rights for accessing those directories and those directories are mandatory system directories for your web hosting.

The ```web``` directory can contain the following directories:

 - **error**
 - **stats**

## Index Files of your Website

Your website is loaded from a file named ```index```. It can have a different file extension according to its type. The following is a list of allowed names. File names must be lowercase.

```index.html, index.php, index.xhtml, index.htm```

## Filesystem

We use Unix file systems on our servers and all filenames are **case sensitive**. It means that file ```index.html``` and ```Index.html``` are two different files.

We recommend you to use only English alphabet characters, numbers, periods, hyphens, and underscores in file names.

## Filesystem limits

### Quota

The max. amount of data on your account is limited depending on your Membership. Every single web hosting (domain, subdomain) has to have configured Quota - the max. amount of data that can be placed on that particular web hosting. You configure the quota value when creating a new web hosting in your Hosting Control Panel. You can also change the quota value anytime in Hosting Control Panel. Max. allowed quota has to be lower or equal than your Membership Quota limit.

If you reach the quota limit on your website, you will be not able to upload more files to this web hosting. Also, your PHP applications will be not able to create session files, upload files, etc.

If you reach 90% of quota usage on your web hosting, you will be not able to upload any new files over FTP. Uploading and interacting with the filesystem within PHP will work.

In both cases described above, you need to remove some data or increase the quota in Hosting Control Panel. If you are out of the limit on your Membership, ask our Support team for help.

### Number of files (inodes)

In addition to quota limits, we also limiting max. number of files for every web hosting. This limit depends on Quota settings and is calculated automatically.

**The basic formula is:** for every 1GB of storage space belongs 10 000 files