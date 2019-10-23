# FreeTDS compiled by Navigating Cancer SRE

This is an unmodified build of FreeTDS 1.1.20, with certain features
enabled with compile flags. Mainly OpenSSL (which is not included in
Debian/Ubuntu's apt repos, due to licensing issues mentioned below.)

This build sets a default TDS protocol version to 7.3 (SQL Server 2008). This can be overridden
via freetds.conf or by TinyTDS/any other client, so is merely a best fallback default.

See http://www.freetds.org/userguide/choosingtdsprotocol.htm for more information on TDS protocol versions.

### Compile Flags in this Package

* *`--with-openssl`* This is compiled with OpenSSL support. Requires OpenSSL > 1.0.1.
* *`--with-tdsver=7.3`* (As mentioned above)
* *`--enable-msdblib`* (Enable Microsoft behavior in the DB-Library API where it diverges from Sybase's.)
* *`--enable-krb5`* (Enable Kerberos support. With Kerberos you can connect to server using your stored Kerberos ticket.)
* *`--disable-debug`* (Removes debug symbols for performance)


### Building Debian Package

Originally this was built with the debmake tools. This version is building with 'checkinstall'
From freeTDS source directory
```bash
sudo apt install checkinstall
 ./configure --with-openssl --enable-msdblib --enable-krb5 --enable-krb5 --with-tdsver=7.3
 sudo checkinstall
```

#### Install Notes

During the checkinstall process it will ask a few questions, enter 'no' to all of them.

I set the following for the build values:

```
0 -  Maintainer: [ sre@navigatingcancer.com ]
1 -  Summary: [ NC FreeTDS with OpenSSL ]
2 -  Name:    [ freetds ]
3 -  Version: [ 1.1.20 ]
4 -  Release: [ 1 ]
5 -  License: [ GPL ]
6 -  Group:   [ checkinstall ]
7 -  Architecture: [ amd64 ]
8 -  Source location: [ freetds-1.1.20 ]
9 -  Alternate source location: [  ]
10 - Requires: [  ]
11 - Provides: [ freetds ]
12 - Conflicts: [  ]
13 - Replaces: [  ]
```

## Legal

FreeTDS is licensed under the GNU GPLv2. See [COPYING](COPYING).

The OpenSSL license requires mentioning of this:

This product includes software developed by the OpenSSL Project for use in the OpenSSL Toolkit (http://www.openssl.org/).
