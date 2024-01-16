# SMTP Mail Plugin: A Simple Guide

The SMTP Mail Plugin lets you send emails using any SMTP server.

## Before You Start

## Configure the plugin

Just follow these easy steps to configure the plugin:

1. Title: Give your plugin a name.
2. Host: Enter the address of your SMTP server. No prefixes needed.
3. Port: The port number of your SMTP server, usually 587.
4. Username: (If needed) Your SMTP server login name.
5. Password: (If needed) Your SMTP server password.
6. Protocol: (Optional. Default = “smtp”) The email protocol you're using.
7. Debug: (Optional. Default = true) Turn this on to find and fix problems.
8. Auth: (Optional. Default = true) Let the plugin know if it needs to log in.
9. StartTlsEnable: (Optional. Default = true) This sets up secure TLS encryption.

## Available actions


### Send email

To send emails during a process:

1. Create a service task.
2. Select the SMTP plugin and fill in the required details:
   1. Sender: Who's sending the email.
   2. Recipients: The main people you're emailing.
   3. CC: Others who need a copy of the email.
   4. BCC: People who get the email without others knowing.
   5. Subject: What your email is about.
   6. Content: The resource id of the main message in your email.
   7. Attachments:  The resource id of any files you want to include.

Tip: Use process variables/process links to manage these details more efficiently and to select multiple items for email and attachments.
A general description on how to create process links can be found [here](../../process-link/create-process-link.md).

## Creating the Email Body
This plugin doesn't create the email body. You'll need to:

1. Make your email content separately. 
2. Store it in Valtimo temporary storage. 
3. Add any attachments to the Valtimo temporary storage. 
4. Save the resource id of step 2 and 3 and pass it as argument in Content and Attachments.

You can use tools like SmartDocuments or upload documents in Form.io  to generate and store content.

Important: The Valtimo temporary storage isn't permanent. If the server or Docker container restarts, the data will be lost.