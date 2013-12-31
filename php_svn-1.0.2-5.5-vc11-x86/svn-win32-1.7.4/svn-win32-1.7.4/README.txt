This is Subversion for Win32, version 1.7.4. Read the CHANGES file to
see what changed in this release:

    http://svn.collab.net/repos/svn/branches/1.7.x/CHANGES

These binaries were built with:

    APR 1.4.5
    APR-util 1.3.12
    APR-ICONV 1.2.1
    Neon 0.29.6
    Berkeley DB 4.8.30
    OpenSSL 1.0.0g
    ZLib 1.2.6
    Apache 2.2.22
    Python 2.5.4 , 2.6.6 and 2.7.2
    Perl 5.14.2 (ActivePerl)
    libintl 0.14.1 (patched)
	Java 1.6.0_30
    Ruby 1.8.6
    Cyrus SASL 2.1.23
    serf 1.0.1
    sqlite 3.7.10.0
    SWIG 1.3.24   (newer versions doesn't work with VC++6)

The BDB binaries are at

    http://subversion.tigris.org/servlets/ProjectDocumentList?folderID=688

The patched libintl is at

    http://subversion.tigris.org/files/documents/15/20739/svn-win32-libintl.zip

Please read the Subversion INSTALL file for more information:

    http://svn.apache.org/repos/asf/subversion/trunk/INSTALL
    


Package contents:

    svn-win32-1.7.4/
       README.txt           -- This file
       bin/                 -- All Subversion binaries and supporting DLLs,
          *.exe                including APR DLLs
          *.dll
          *.pdb
          mod_*_svn.so      -- Apache modules
          mod_*_svn.pdb
       doc/                 -- Doxygen documentation
          *.html
          *.css
          *.png
       iconv/               -- All apr-iconv loadable modules
          *.so
          *.pdb
       include/             -- Include files (for development)
          *.h
          apr/
             *.h
          apr-util/
             *.h
          apr-iconv/
             *.h
       javahl/              -- Java HighLevel wrapper library
          *.jar
          *.dll
          *.pdb
       lib/                 -- Library files (for development)
          libsvn*.lib
          apr/
             *.lib
             *.pdb
          apr-util/
             *.lib
             *.pdb
          apr-iconv/
             *.lib
             *.pdb
          neon/
             *.lib
             *.pdb
          serf/
             *.lib
             *.pdb
          sasl/
             *.lib
             *.pdb
       licenses/            -- Various license files
       perl/                -- Perl language bindings
          site/lib/SVN/
             *.pm
          site/lib/auto/SVN/
             *.dll
             *.pdb
       python/              -- Python language bindings
          libsvn/
             *.py
             *.pyd
             *.dll
             *.pdb
          svn/
             *.py
       ruby/                -- Ruby language bindings
       share/
          locale/           -- Message translations

For a nice description of setting up Subversion on a server on Windows, see the
developer edition of the TortoiseSVN Manual, Chapter 3, Setting Up A Server:

   http://tortoisesvn.net/docs/nightly/TortoiseSVN_en/index.html

For an Apache server here's the essentials:

1. Copy bin/mod_dav_svn.so and bin/mod_authz_svn.so to the Apache modules directory.
2. Add the Subversion/bin directory to the SYSTEM PATH and reboot so all the Subversion
   support dll's are visible to the Apache service.
3. Edit the Apache configuration file (httpd.conf) and make the following changes:

  3a. Uncomment the following two lines:

      #LoadModule dav_fs_module modules/mod_dav_fs.so
      #LoadModule dav_module modules/mod_dav.so

  3b. Add the following two lines to the end of the LoadModule section:

      LoadModule dav_svn_module modules/mod_dav_svn.so
      LoadModule authz_svn_module modules/mod_authz_svn.so

  3c. Add the following to end of the file. Note: This Location directive is a
      minimal example with no authentication directives. For other options,
      especially authentication options, see the Subversion INSTALL file,
      the Subversion Book, or the TortoiseSVN Manual.

      <Location /svn>
        DAV svn
        SVNPath your/repository/path
      </Location>
