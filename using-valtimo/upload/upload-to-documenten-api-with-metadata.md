# Uploading to Documenten API with metadata

The Documenten API is an API for storage and disclosure of documents and associated metadata. Valtimo supports uploading
files to the Documenten API with the option to input metadata through a dedicated tab on the detail page of a case
instance.

## Configuring the front-end implementation

To enable the dedicated Documenten API tab in an implementation, set `uploadProvider` in the implementation's
environment file to `UploadProvider.DOCUMENTEN_API`. The documents tab on a case detail page will now show the
Documenten API uploader.


