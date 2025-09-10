# 13.1.0

## New Features

#### Case definition list columns and search fields

List columns and search fields can now be configured via a JSON Editor under the Case definition details.

#### Dashboards widget configuration

Dashboard widget configurationscan now be edited via a JSON Editor under the dashboard details.

#### Notificaties API improvements

When working with the Notificaties API, it is important to keep subscriptions (abonnementen) as specific as possible. 
Otherwise, the Notificaties API will send more messages than Valtimo is interested in, leading to more stress on both
systems.

Valtimo more accurately determines which channels (kanalen) should be subscribed to, with accompanying filters to reduce this
stress as much as possible. This is done by evaluating plugin configurations that depend on the Notificaties API, such
as the Portaaltaak plugin and the Verzoek plugin. Lastly, all channels that are subscribed to are combined into a
single subscription.
