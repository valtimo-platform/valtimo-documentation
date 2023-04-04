# Case count

Cases may be assigned to a user (for more information, consult [this page](assigning-a-user.md)). The
number of unassigned cases for a certain case type can be shown in the side navigation bar. The open case count may be
retrieved in a number of ways.

## Feature toggle

For the unassigned case count to display, the feature toggle `disableCaseCount` must not be enabled. For more
information, consult [this page](/reference/feature-toggles.md).

## Case type should be assignable

Secondly, for the unassigned case count for a certain case type to display, it must be possible to assign a user to
a case of this type. For more information, consult [this page](assigning-a-user.md).

## Retrieve count through timer

If the above-mentioned criteria are met, the unassigned case count for each case type will be retrieved every five
seconds by default. In order to reduce resource usage, and to display changes in the unassigned case count sooner,
the count may be retrieved in response to Server-Sent Events (SSE). Consult the next paragraph for instructions on how
to enable this.

## Server-Sent Events (SSE)

Server-Sent-Events enable the server to notify the application running in your browser when something changes. This
improves efficiency, since data is only retrieved when it might have changed. Follow the below instructions on how to
retrieve the unassigned case count in response to Server-Sent-Events.

## Include SSE in your application

Firstly, make sure your back-end implementation includes the SSE module. Also, make sure your front-end implementation
has the `@valtimo/sse` dependency included.

## Configure front-end to use SSE for unassigned case count

The unassigned case count is retrieved in the front-end through a service implementing the interface
`DocumentCountService`, which is exported by `@valtimo/components`. By default, the service `DocumentCountTimerService`
(exported by the same library) is used for this purpose.

Any other service conforming to this interface may be used to retrieve the unassigned case counts. The library
`@valtimo/sse` exports the service `DocumentCountSseService`. In order to use this service (or any other service
implementing the interface) for retrieving the unassigned case count, include the following in your app module:

#### **`app.module.ts`**

```typescript
import {
    ...
    DOCUMENT_COUNT_TOKEN
} from '@valtimo/components';
...
import {DocumentCountSseService} from '@valtimo/sse';

...

export class AppModule {
    ...
    providers: [
        ...
        {
            provide: DOCUMENT_COUNT_TOKEN,
            // specify a service implementing the interface DocumentCountService
            useValue: DocumentCountSseService,
        }
    ],
    ...
}
```