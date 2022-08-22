# Migration

This page describes how to update Valtimo from the previous to this version.

* **FormFieldDataResolver supports method**
    
    A new supports method `supports(externalFormFieldType: String)` replaces the
    already existing `supports(externalFormFieldType: ExternalFormFieldType)` method
    for the `FormFieldDataResolver` interface.

  1. **Replace uses of old method with new method**

     If the old method was used, the new method can be used by converting the
     existing argument to a string.

  2. **Implement new supports method**

     For classes implementing the `FormFieldDataResolver` interface, the new method
     should be implemented.
