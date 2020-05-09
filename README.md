# ag-sync
Utilities to synchronize server-level objects (currently just logins) across availability groups.

Copyright Daniel Hutmacher under [Creative Commons 4.0 license with attribution](http://creativecommons.org/licenses/by/4.0/).

Source: http://sqlsunday.com/downloads/

DISCLAIMER: This script may not be suitable to run in a production
            environment. I cannot assume any responsibility regarding
            the accuracy of the output information, performance
            impacts on your server, or any other consequence. If
            your juristiction does not allow for this kind of
            waiver/disclaimer, or if you do not accept these terms,
            you are NOT allowed to store, distribute or use this
            code in any way.

            Please test stuff before you put it in your
            production environment.

**USAGE:**

    EXECUTE dbo.SyncLogins
       @primary_replica,                -- {name of SOURCE linked server}
       @allow_drop_logins,              -- 1=allow script to drop logins
       @print_only,                     -- 1=only print the T-SQL.
       @check_policy                    -- 1=force check password policy to on
       @exclude_logins                  -- comma-separated list of logins to exclude. Example: 'abc,def,DOMAIN\ghi'

TODO:
* Owners of logins.
* Permissions on endpoints.
