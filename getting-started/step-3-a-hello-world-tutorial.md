# 🔥 Step 3: A "Hello World" tutorial

One of the strong sides of helmut.cloud is collaboration. To make it as easy as possible for users, everything is organized around organizations.

Your personal account already is a "one person organization" where you can start building for yourself. If you want to go out there and work with others, you should create or join an organization.

## Create your own organization

To start working, set up your first organization.

* Click on your avatar-icon in the upper right corner
* Choose "My organizations"
* Click on "Create an organization"
* Give it a name that makes sense to you

Gratulations! You are now the owner of an organization! From now on, you can create workflows and add members to your organization.

## Create a workflow in High5

### Make some space

A space is a good starting point for your workflow. It will allow to manage all the important details about it while maintaining order.

* Go to High5 - Spaces and click on "Create Space"
* Give it a name that makes sense to you (like 'Playground') and click "C_reate_"

Now your space is listed in High5 and can be entered.

### Already hooked?

Every workflow needs a starting point. In helmut.cloud, _events_ are used to induce workflows and trigger the programs that we call streams. So every event has a stream assigned that executes whatever you programmed it to do.

If you want an outside source to trigger your workflow, like a cloud service with webhook support or your own server, you could use a webhook as event trigger.

Let's make a webhook and trigger it with a curl command from terminal to execute the stream we are going to build later. Create an event and name it "TestEvent", for example. You will see that your event is empty, meaning: It does not contain a stream yet.

We create a webhook anyway. Click on the webhook-icon next to the events name, and configure a webhook that we could name "TestEventWebhook". It triggers our event "TestEvent", and your personal account will be the target, so fill in your accounts e-mail address.

If you do not want unauthorized parties to execute your webhook, secure it with additional headers or an HMAC signature and a preshared key. Both can be added below "Advanced options".

To make it easy in this tutorial, we will use a header and a password. My header key will be "knockknock" and the value will be "itsme". Click "_Create_" and your webhook is ready. As we can copy the link again later, I will just close the window to proceed with my stream.

### Automate your workflow: create a stream

Go back to the events from your Playground-space and find your TestEvent. To eventually build the workflow logic and automate something, let's add a stream with "_+ Add stream_".

Our "TestStream" can be created and then entered by clicking on it. The StreamDesignerStudio will open, allowing you to define a workflow programmed in a graphical user interface.

In this stream, we will build a simple logic: Whenever the webhook is being triggered, a website opens in our webbrowser.



## Install and configure your helmut.cloud agent
