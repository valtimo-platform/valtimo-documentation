# Frontend libraries 5.10.0 (RC)

## New Features

The following features were added:

* **Sorted processes in progress tab**

  The processes that are displayed in the progress tab are now sorted with active processes first.

* **System processes**
  Processes can now be marked as a system process. System processes are processes that are critical
  to the functioning of Valtimo itself. When a process is marked as a system process it will be shown 
  in the list of processes and when viewing a process. If the process is also marked as read-only it
  will not be editable from the frontend.

  More information about this feature can be found [here](/using-valtimo/process/systemprocesses.md).

* **Added environment property to set the supported filetypes for uploading a file**
  
  A new property `caseFileUploadAcceptedFiles` can be used in the environment file to whitelist the supported filetypes 
  when trying to upload a file in the documents tab.

  The way to use this is to create a comma separated list of mime types or file extensions.
  
  Eg.: `image/*,application/pdf,.psd`


## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Breaking change1**

* **Breaking change2**

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **Deprecation1**

  X was deprecated and is replaced with Y.
* **Deprecation2**

  X was deprecated and is replaced with Y.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Known issues

This version has the following known issues:

* **Issue1**
    * Discovered in version x.x.x
    * Describe what can be done to work around the issue

* **Issue2**
    * Discovered in version x.x.x
    * Describe what can be done to work around the issue
