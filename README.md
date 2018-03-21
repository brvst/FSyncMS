FSyncMS
=======

PHP Sync Server for Firefox/Pale Moon Sync
An extension of the Weave-Minimal Server.

More information about the original implementation of this server, past versions, etc.
can be found here:

https://www.ohnekontur.de/category/technik/sync/fsyncms/

Although the original author has planned further extensions to this implementation,
the current state of this server implementation is rather stagnant and missing two
important features:
* Delete account from the web
* Reset password from the web (similar to reset inside the client)

Current state is the state as-used by the Pale Moon Sync service, which is v0.14.

If you wish to help complete the missing features, please feel free to clone this repository and make 
the necessary edits -- kindly submit a pull request after you've tested your changes so it can be merged
back in and improve this software!

Release notes for older original versions:

FSyncMS v0.14
======

- Improved database update efficiency (use INSERT with duplicate key detection)
- Implemented hard quota cap
- Implemented soft quota cap
- Reduced returned server information on error
- Implemented warning level header

FSyncMS v0.13.1
======
Password Change Bug-fix

There has been a bug in FSyncMS v 0.13: if you tried to update your password via Firefox, the wrong hash
was written in the Database. As a result the account was no longer usable, but no data should be lost.
This update fixes the Bug.

FSyncMS v0.13
======
Database upgrade
for more information and some migration notice see
http://www.ohnekontur.de/2013/07/05/fsyncms-version-0-13-database-upgrade/


FSyncMS v0.12
======
Compatibility update 

FSyncMS v0.11
======
Added dedicated setup script, which will create the database and the config file: settings.php

If you want to create it by your own, just generate the settings.php with the following content

    <?php
        //you can disable registration to the firefox sync server here,
        // by setting ENABLE_REGISTER to false
        //
        //
        //define("ENABLE_REGISTER",false);
        define("ENABLE_REGISTER", true);


        //pleas set the URL where firefox clients find the root of 
        // firefox sync server
        // this should end with a /
        //
        define("FSYNCMS_ROOT","https://DOMAIN.de/Folder_und_ggf_/index.php/");

        //MYSQL Params
        define("MYSQL_ENABLE", false);
        define("MYSQL_HOST","localhost");
        define("MYSQL_DB","databaseName");
        define("MYSQL_USER", "databaseUserName");
        define("MYSQL_PASSWORD", "databaseUserPW");

    ?>


FSyncMS v0.10
======
MYSQL Support

FSyncMS v 0.9
======
Change Password now supported 
working with firefox 12 (and lower)

Changelog:
Added change Password feature

FSyncMS v 0.8
======
Should be working with firefox 11 and lower (tested with 11)

Changelog:
Fixed user registration process,
fixed some delete problems
