# Frontend libraries 10.5.0

## New Features

The following features were added:

* **Use new endpoint to retrieve documents from the Zaken API**

  When `uploadProvider` is set to `UploadProvider.DOCUMENTEN_API` in the environment file, a custom documents page is
  displayed under the documents tab on a case detail page. The documents displayed in the table on this page are now
  retrieved using a Zaken API plugin configuration, by using the new endpoint included in this release:

  `${this.valtimoEndpointUri}v1/zaken-api/document/${documentId}/files`

* **Sort files on documents tab on case detail page by date**

  A feature toggle has been added to enable sorting files related to a case on the documents tab of the case detail page
  by date in descending order. In order to use this, use the `sortFilesByDate` feature toggle. For more information,
  refer to [this page](/reference/feature-toggles.md).

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
