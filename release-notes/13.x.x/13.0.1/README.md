# 13.0.1

## Bugfixes

* When deploying a decision definition that is not part of a case definition, it now no longer replaces the previous 
version but instead adds a new one.
* When creating a new case definition now the default case tabs are again automatically created.
* Fixed a bug where plugin actions would sometimes not be available from the process link screen.
* Process links for global processes are now correctly imported again when import files are located in the 
`config/global/process-link` folder.
