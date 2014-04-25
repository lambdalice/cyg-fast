cyg-fast
=======

cyg-fast is an advanced version of apt-cyg, command-line installer for [Cygwin](http://cygwin.com/) which cooperates with Cygwin Setup and uses the same repository. 

Supporting pre-resolving dependencies and parallel-downloading, cyg-fast works faster than apt-cyg.

The syntax is similar to apt-get. Usage examples:

* "cyg-fast install &lt;package names&gt;" to install packages
* "cyg-fast resume-install" to resume interrupted installing
* "cyg-fast remove &lt;package names&gt;" to remove packages
* "cyg-fast update" to update setup.ini
* "cyg-fast show" to show installed packages
* "cyg-fast find &lt;pattern(s)&gt;" to find packages matching patterns
* "cyg-fast describe &lt;pattern(s)&gt;" to describe packages matching patterns
* "cyg-fast packageof &lt;commands or files&gt;" to locate parent packages
* "cyg-fast pathof &lt;cache|mirror|mirrordir|cache/mirrordir&gt;" to show path"
* "cyg-fast build-deptree" to build dependency tree to make install/remove faster

Requirements
-----------

cyg-fast requires the cygwin default environment and optional packages below.

* aria2

Quick start
-----------

cyg-fast is a simple script. Once you have a copy, make it executable:

    # chmod +x /bin/cyg-fast

Optionally place cyg-fast in a bin/ folder on your path.

Then use cyg-fast, for example:

    # cyg-fast install vim

New features
------------

### Parallel downloading with aria2

Aria2 is an advances file downloading tool that allows you to download files with faster speed.

cyg-fast provides multi-connection downloading using aria2.

You can change the maximum number of connections with the ```--max-connections``` option.

### True multi-architecture support

Let think a case that you want to install the x86 package when you are working under the x86_64 environment.
For example:

    # cyg-fast --charch x86 install chere

As of 2013-10-26, chere package is provided for only the repository for x86.

Remarks:
Of course, you must install both environments of x86_64 and x86, beforehand.

### Pre-resolving dependencies

cyg-fast finds all depending packages before downloading and installing.

### Generate dependency tree and check dependency on removing

You can generate "dependency tree" using ```cyg-fast build-deptree```

to make installing faster and enable dependency checking on removing.

Generated dep-tree is in $cache/$mirrordir/$arch/deptree .

### Resume installation when downloading fails

Type ```cyg-fast resume-install``` to resume interrupted downloading.

You don't need to be annoy with an unstable internet connection...

### Force re-install packages

You can reinstall a package by using ```cyg-fast --force install <package>```

### Rapid mode

If you are hurrying to install some packages, use ```--rapid``` to avoid wasting time 
by updating setup.ini, checking certificates, checking signatures, checking MD5s, etc.

Contributing (original apt-cyg)
-------------------------------

This project has been re-published on GitHub to make contributing easier. Feel free to fork and modify this script.

The [Google Code project](https://code.google.com/p/apt-cyg/) has a list of open issues.

### Forks on the github

Caution:
Please do not merge forks that have incompatible licenses.

Ex.) Merging to the GPL from the MIT is possible. But merging to the MIT from the GPL  is impossible.

#### Official (MIT license)

* [transcodes-open / apt-cyg](https://github.com/transcode-open/apt-cyg/network)

#### Unofficial (GPLv2)

* [cfg / apt-cyg](https://github.com/cfg/apt-cyg/network)
* [ashumkin / apt-cyg](https://github.com/ashumkin/apt-cyg/network)
* [svn2github / apt-cyg](https://github.com/svn2github/apt-cyg/network)
* [nosuchuser / apt-cyg](https://github.com/nosuchuser/apt-cyg/network)
* [kazuhisya / apt-cyg64](https://github.com/kazuhisya/apt-cyg64/network)
* [bnormsoftware / apt-cyg](https://github.com/bnormsoftware/apt-cyg/network)
* [rcmdnk / apt-cyg](https://github.com/rcmdnk/apt-cyg/network)
* [buzain / apt-cyg](https://github.com/buzain/apt-cyg/network)
* [wuyangnju / apt-cyg](https://github.com/wuyangnju/apt-cyg/network)
* [takuya / apt-cyg](https://github.com/takuya/apt-cyg/network)

