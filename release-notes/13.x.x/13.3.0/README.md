
# 13.3.0

## Bugfixes

* Case widgets of type FormIO will now correctly finish loading and no longer cause the widget
  page to be stuck on a loading animation.
* The document files endpoint in the Documents tab is now called only once, improving performance and preventing duplicate requests when many documents are linked to a case.
* The task status shown in the case details is now fully visible, ensuring the status text is no longer partially cut off.
