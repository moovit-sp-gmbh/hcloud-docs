# MacOS

* Download the most recent .pkg installer
* As long as the installer is unsigned, open it with a right-click and choose "_Open_" from context-menu
* MacOS will warn you that the installer cannot be verified - choose okay, as we have not signed the installer yet
* Follow along the installation routine and finish installation

The HCloud.app will be installed into the _Applications_ folder on your Mac.

## Set privileges for HCloud.app in System Preferences

To allow HCloud.app access to folders inside your users home like Desktop, Downloads or Documents, you will need to set privileges.

Open _System Preferences_ via the Apple icon in the upper left corner of your Mac. Navigate to "_Privacy and Security_". Here, you can set granular privileges in _Files and Folders_ or add _HCloud.app_ to _Full Disc Access_, if your workflow demands it. If you are running HCloud.app unattended, consider to set full disc access to avoid requests blocking your executions.

_You should always consider the apps and the OS users privileges in your environment and set them according to your workflows needs and to internal security guidelines._
