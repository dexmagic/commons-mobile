# commons-mobile Readme File

July 13, 2023

This repository contains mobile projects that compile the Apache commons libraries as libraries on mobile devices.

As of this writing the only device the code is ported to is Android.

The apache commons libraries are included as submodules.
In order to build the mobile projects you first have to checkout the modules.

Here is how to get started:

```
$ git clone git@github.com:dexmagic/commons-mobile.git
Cloning into 'commons-mobile'...
remote: Enumerating objects: 145, done.
remote: Counting objects: 100% (145/145), done.
remote: Compressing objects: 100% (63/63), done.
remote: Total 145 (delta 67), reused 142 (delta 64), pack-reused 0
Receiving objects: 100% (145/145), 1.46 MiB | 4.69 MiB/s, done.
Resolving deltas: 100% (67/67), done.

$ cd commons-mobile 

$ git submodule update --init
Submodule 'commons-math' (git@github.com:apache/commons-math.git) registered for path 'commons-math'
Submodule 'commons-numbers' (git@github.com:apache/commons-numbers.git) registered for path 'commons-numbers'
Submodule 'commons-rng' (git@github.com:apache/commons-rng.git) registered for path 'commons-rng'
Submodule 'commons-statistics' (git@github.com:apache/commons-statistics.git) registered for path 'commons-statistics'
Cloning into '/Users/richard/Development/git-dexopruntime/apache/test/commons-mobile/commons-math'...
Cloning into '/Users/richard/Development/git-dexopruntime/apache/test/commons-mobile/commons-numbers'...
Cloning into '/Users/richard/Development/git-dexopruntime/apache/test/commons-mobile/commons-rng'...
Cloning into '/Users/richard/Development/git-dexopruntime/apache/test/commons-mobile/commons-statistics'...
Submodule path 'commons-math': checked out '2fb5f6aa950cae4cca7997bfd3990e35eda4cef2'
Submodule path 'commons-numbers': checked out '447138604bb57541fe24d0b0ac5e6d838f2935c2'
Submodule path 'commons-rng': checked out '64ad1e63c9895e974d57fff925d6be896c7a9975'
Submodule path 'commons-statistics': checked out '763ba719c5972488c2fa76901f50faa5124440e5'

```

After you clone this repo and the submodules you can open the Android Studio project in ```commons-mobile/android``` and build the project.

## Building

Android Studio often defaults to using the Amazon Coretto JDK to build project, and this causes issues in the build sometimes. You may see this error:

```
A problem occurred configuring root project 'commons-math'.
> Could not resolve all files for configuration ':classpath'.
   > Could not resolve com.android.tools.build:gradle:8.0.1.
     Required by:
         project : > com.android.application:com.android.application.gradle.plugin:8.0.1
         project : > com.android.library:com.android.library.gradle.plugin:8.0.1

... etc ...

```


So, in order for Android Studio to build the project make sure that your Java compiler is set to a newer version of JDK.

```
Android Studio -> Setting -> Build, Execution, Deployment -> Build Tools -> Gradle -> Gradle JDK:
	set to a JDK version higher. Oracle Open JDK 18 is recommended.
	this project was last built with Oracle OpenJDK 18.0.2.
```





