# FreeTDS compiled by Navigating Cancer SRE

This is an unmodified build of FreeTDS 1.00.54, with certain features
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


### Debian Control Data
```
Source: freetds
Section: libs
Priority: extra
Maintainer: Navigating Cancer SRE Team <sre@navigatingcancer.com>
Build-Depends: debhelper (>=9), dh-autoreconf, openssl (>=1.0.1)
Standards-Version: 3.9.6
Homepage: https://github.com/NavigatingCancer/freetds

Package: freetds
Architecture: any
Multi-Arch: foreign
Depends: ${misc:Depends}, ${shlibs:Depends}
Description: FreeTDS 1.00.54 SQL Server Libraries
 Aug 2017 by Arthur Kepler @ Navigating Cancer SRE.
 Compiled with OpenSSL, Kerberos5, and TDSver=7.3 flags.
 Version 1.00.54 - FreeTDS Stable
 Package generated by debmake
```
## Legal

FreeTDS is licensed under the GNU GPLv2. See [COPYING](COPYING).

The OpenSSL license requires mentioning of this:

This product includes software developed by the OpenSSL Project for use in the OpenSSL Toolkit (http://www.openssl.org/).


