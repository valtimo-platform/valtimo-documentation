# Creating a process link

Plugin actions can be attached to Camunda activities through process links. A process link can be configured in the
process link menu. The process link menu is found under the admin menu. Admin privileges are required to configure
process links.

1. Go to the Admin menu
2. Go to the 'Process connection' menu
3. Select the task of the desired process
4. Follow the steps

![Using a plugin](img/use-plugin.png)

Any text fields for configuring the process link itself support several ways of providing values through value
resolvers:

1. A fixed value. This value will be put directly into the template without alterations. For example `John`
2. A value retrieved from the case-data. This value should start with `doc:` and should end with the path to the
   case-data property. For example `doc:/firstname`.
3. A value retrieved from a process variable. This value should start with `pv:` and should end with the name of the
   process variable. For example `pv:firstname`.
