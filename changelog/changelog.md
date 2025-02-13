# 🎉 Changelog

## 13-02-2025

### Frontend

**New features and enhancements**

* Added a notification toast when user settings are updated.
* Added a password-reveal icon for the `currentPassword` field on the account page.
* Password fields are now cleared automatically after a successful password change.
* Improved email validation to support addresses like `j.doe+alias123@example-mail.com` for active organizations.
* Implemented a workflow to invite unregistered users to join an organization.
* Introduced a new table view component.

**Bug fixes**

* Fixed an issue where `spaceName` was not being resolved when navigating from `space > webhooks` to `home`.

**Changes**

* Removed filtering for the creator field.

### Stream Designer Studio

**New features and enhancements**

* Enhanced the **Quick Add Node** component.
* Replaced the string input field in the SDS menu with a text area.
* Introduced a **wildcard panel**.
* Added a new `STRING_PASSWORD` input field.
* Added functionality to persist stream tabs even after a browser tab is reloaded.
* Improved navigation experience on the canvas.
* Improved the look of stream tabs.

**Bug Fixes**

* Fixed a bug where toggling the select button on one node catalog card incorrectly affected all toggle buttons.
* Fixed layout issues with logs, information, payload, and performance sections in the SDS debugger.
* Fixed an issue where `STRING_SELECT` inputs displayed the label instead of the value..
* Fixed an issue where the rename snapshot icon was missing when hovering over a snapshot card.

### High5

**Bug fixes**

* Fixed an issue where extra white spaces in payload values were being removed incorrectly.
* Fixed an issue where High5 failed to check the minimum engine version before executing a stream.
* Fixed an issue where webhook logs displayed incorrect source IP addresses.

### Wave engine

**New features and enhancements**

* Added **color and node type** to `nodeResult`.
* Implemented the initial support for **stream debugging**.
* Improved **logging reliability**, including a mechanism to **report crashes when regular logging fails**.
* Enhanced logging with:
  * A `logs` property in `nodeResult`.
  * A new `addNodeLog()` helper method.
  * Support for the `logs` wildcard.

### Agent

**New features and enhancements**

* Improved how the agent **handles connection failures**.
* Implemented the initial support for **stream debugging**.
* Added a **reconnection mechanism** in `ContextManager`.
* Added an **uninstaller** to clean up the `.hcloud` directory.
* Introduced **new endpoints to get and set bundle versions**.

**Bug Fixes**

* Fixed issues with **bundle version headers**.
* Fixed an issue where the **initial context setup** was unnecessarily delayed.

## 10-11-2024

### **Wave engine**

**Bug Fixes**

* Resolved an issue where wildcards could not be resolved.
* Corrected access rights for publishing logs.
* Fixed issues executing certain file and folder nodes on Windows.
* Improved logic for managing additional node connectors.

**New features and enhancements**

* Added type support in node execution logs.
* Introduced helper methods for folder creation management.
* Expanded wildcard support:
  * `{{node.<nodeId>.input.Inputname}}`
  * `{{node.<nodeId>.output.outputname}}`
  * `{{node.<nodeId>.errors}}`
  * `{{node.<nodeId>.info.*}}`
  * `{{stream.info.*}}`
  * `{{agent.info.*}}`

### **Miscellaneous**

**New features and enhancements**

* Added changelogs for Wave Engine, Wave Nodes, Agent Bundle, and Agent.

**Bug fixes**

* Admins can no longer invite owners.

### **Frontend**

**Bug fixes**

* Improved table filter functionality.
* Org dropdown now auto-refreshes after creating a new org.

**New features and enhancements**

* Added full support for real-time updates.
* Introduced a password complexity checker to all password-entry views.
* Reworked QR Code generation process.

### **Fuse**

**Bug fixes**

* Fixed an issue where Fuse was not sending payloads to a High5 webhook URL.

### **Stream Designer Studio (SDS)**

**Bug fixes**

* Resolved issues with copying and pasting nodes between stream tabs.
* Fixed streams containing extended ASCII characters that failed during exchange.
* Resolved pagination issues in the custom nodes panel.
* Fixed node inputs not appearing in the debugger when a node fails.
* Corrected text overflow issues in specific scenarios.
* Fixed extended ASCII character rendering in the debugger's payload panel.
* Improved mouse-down events for smoother interactions.

**New features and enhancements**

* Added language support in the extended input window.
* Enabled stream testing without prior publishing.
* Redesigned debugging experience with a payload view and info section.
* Introduced node catalog store and stream tabs.
* Added Quick Add feature for faster node additions.
* Implemented a command palette for improved navigation:
  * Moved test dialog, snapshot dialog, connect agent dialog, settings, and shortcuts to the command palette.
* Enhanced snapline behavior for nodes and annotation nodes.
* Introduced confirmation dialog when closing unsaved streams.
* Added full Markdown support for annotation nodes.
* Enabled snapshot renaming and disabled deletion for published snapshots.
* Introduced support for Stream Node Specification v2.
* Added option to disable animations in SDS.
* Included font size slider in the settings menu.
* Improved zoom and pan behavior for trackpads and scroll wheels.
* Redesigned snackbars for better appearance and positioning.
* Enhanced UI for renaming nodes.

### **Platform OpenAPI**

**Improvements**

* Made multiple updates to OpenAPI files.

### **Wave node blueprint**

**New eeatures and enhancements**

* Added a sample test folder.
* Provided extended documentation for helper methods, node specifications, building, and publishing nodes.
* Added support for `changelog.json` and development releases.

### **Agent**

**Bug fixes**

* Multiple fixes for the Windows Agent, including system tray icon issues.
* Resolved issues with SSL certificate loading.
* Fixed startup failures on macOS and Windows.

**New features and enhancements**

* Introduced a new launcher for the Windows Agent.
* Windows installer now creates a desktop icon by default.

**Changes**

* Signed installers for Windows and macOS.

### **High5**

**Bug fixes**

* Multiple fixes to High5 execution logic.
* Fixed streams being published immediately upon creation.
* Clicking on an execution now opens the corresponding logs.

**New features and enhancements**

* Added option to set Wave Engine to always use the latest version.
* Introduced dialog for managing Wave Engine versions.
* Enhanced webhook security with IP blacklists and whitelists.
* Added response option for webhooks.
* Coupled High5 node catalogs with Wave Engines.

### **helmut.cloud Node Catalogs**

**Core catalog**

* **New features**
  * Added Python node, Respond to Webhook node, and File Download node.
  * Included documentation files for all nodes.
  * Added metadata file to the root of the node catalog.
* **Improvements**
  * Enhanced MacOS Command Runner's handling of return codes.

**Beta Catalogs**

* Frame.io Catalog
* Freespace Catalog
* Telegram Catalog
* Cloudflare R2 Catalog
* Hiscale Catalog
* MongoDB Data API Catalog
* Jitbit Catalog

## 02-08-2024

### **helmut.cloud agent**

**Bug fixes**

* Fixed an issue where the agent threw a "reader closed SyntaxError: Unexpected end of JSON input" at startup.
* Fixed the signing process for the macOS installer.
* Fixed an issue that prevented the agent from starting on Windows.
* Fixed an issue preventing the agent from correctly loading the SSL certificate at runtime.
* Fixed a semantic error in the agent's OpenAPI specification.
* Fixed an issue where the agent failed to load certain modules.
* Fixed an issue where the agent wouldn't start if it couldn't find the bundle.
* Fixed some instabilities during the update process to a new bundle.
* Fixed an issue where the agent was reporting non-IPv4 addresses to the backend.
* Fixed an issue where the agent threw "Unable to determine version: 'Error: ENOENT: no such file or directory."
* Fixed multiple issues that prevented the agent from starting on macOS.
* Fixed an issue where the Windows agent would open a terminal window at startup.
* Fixed the issue with disabling the agent connection.
* Resolved an issue where accessing `http://localhost:6968/api/agent/v1/version` returned "unknown" in a Docker container.

**Improvements**

* Updated the agent's ping interval to the backend to 10 seconds.
* Improve the reliability of the agent's ContextManager.
* Exposed the agent's OpenAPI.
* Extended the status bar menu.
* Implemented automatic reconnection logic in case of connection drops.

**Changes**

* Renamed the agent binary from "hcloud agent" to "helmut cloud agent."
* Updated the application name from "HCloud" to "helmut cloud agent."
* Updated icons for the hcloud agent.

### &#x20;**helmut.cloud backend**

**Bug fixes**

* Fixed an issue preventing the agent from registering with the mothership in certain cases.
* Fixed a problem where license updates were not working correctly for private organizations.
* Addressed a database error that occurred when attempting to create a webhook without specifying a target.\


**Improvements**

* Updated the OpenAPI documentation.
* Set wave engine dev images to be skipped by default when creating a space.
* Integrated HMAC encryption into Fuse.
* Prevented users from disabling their account as an execution target in private organizations.



### **helmut.cloud frontend**

**Bug fixes**

* Fixed the icon used for "Win32" OS on the agent dashboard.\


**New features and enhancements**

* Added support for signing up and logging in using Microsoft, Google, GitHub, and Discord.
* Added a description field in the new secret dialog.
* Updated user's avatar menu for better usability.
* Updated the organization selector.
* Enabled auto-focus on the password field on the login page.
* Displayed TOTP during personal access token creation/update when 2FA is enabled.
* Introduced a password complexity checker in the sign-up form.

### **helmut.cloud Stream Designer Studio:**

**Bug Fixes:**

* Fixed an issue where pressing the 'delete' key after selecting text in an input field would delete the selected node.\


**New features and enhancements**

* Made multiple improvements to the functionality of the annotation node.
* Renamed the unconnected fail outputs to "global fail" when the trigger node global fail connector is connected to a node.
* Automatically display alignment guidelines when a node aligns with the top, right, or left side of another node(s).
* Added a collapsible optional inputs field in the node's configuration panel.
* Added the option to rename manual snapshots.
* Disabled the option to delete a published snapshot.
* Prevented input fields from shifting between sections in the Custom Node dialog.
* Added an edit button to the custom node toolbar to the Custom Node dialog.
* Improved the node search panel and overall search experience.
* Improved the dismissal behavior of snapshot and connect agent modals to close when clicking outside the dialog
* Added code editor to the expanded view of the node's input fields.
* Made Multiple improvements to the shortcut modal.



### helmut.cloud Wave engine

**Bug fixes**

* Fixed an infinite loop within the wildcard resolver.
* Fixed issues with the Node Catalogue on Windows.



### helmut.cloud Wave Node Catalog

**New features and enhancements**

* Decoupled the Wave Engine from the Wave Node Catalog.
* Implemented contract-based versioning for the wave node specifications.
* Added Windows support for wave-execution in the development environment.
