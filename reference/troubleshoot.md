# Troubleshoot

## Documents

### "Invalid JSON path expression" when searching for a document

MySQL documentation states "Names of keys must be double-quoted strings or valid ECMAScript identifiers". As a rule of
thumb, if the property contains a hyphen, then the property should have quotes surrounding it.

Searching for `"$.order.order-id"` becomes `"$.order.\"order-id\""`.
