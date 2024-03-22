# The key features of helmut.cloud

To better understand helmut.cloud, it is good to take a look at its key features.

## Organizations

The heart of helmut.cloud. Its strongest side is its way to work together with other helmut.cloud users - be it inside or outside of your own real-life company or team. Collaboration is defined by a users membership to an organization - an abstract organizational layer inside helmut.cloud.

An organization

* is mandatory to act in helmut.cloud,
* defines a users permissions and role for using applications inside helmut.cloud,
* makes it possible to collaborate with members in- or outside of your real-world company or team,
* and keeps all the workflows, secrets and programs that were created in it.

One user can be in multiple organizations, or can have a single organization for themself. In fact, since you registered, you already own a "private one-person-organization" - your account.&#x20;

As everything belongs to organizations, it is easier to switch user roles, assign or revoke memberships to projects without losing data that in conventional systems would be tied to one person only. You can even hand over ownership of an organization to someone else and leave, just to start your next project right away.

Fit your organizations to the projects needs and infrastructure - not the other way around!



## High5

**High5** is the brain of helmut.cloud. High5 helps you to make connections between applications - no matter what, as long as they support some interface for automation (e.g. webhooks or a Rest API). It also gives you the power to control who can do what in your workflows.

High5 allows you to

* manage your event triggers and workflows by organizing them in spaces,
* define variables and secrets that can be used inside a space,
* orchestrate events and actions graphically within the Stream Designer Studio,
* administrate the agents that execute your workflows for you,
* and monitor your workflows in a dashboard.

### Stream Designer Studio

Stream Designer Studio is a graphical programming environment for low-code programs called streams. It is a part of High5. \
You can choose between a variety of nodes that represent single actions, conditions or event triggers. Drag them onto your canvas and connect them in the order you need them to be executed. Build conditions or introduce logic into your workflows, working with data from internal or external applications.&#x20;

As a developer, you can even go all in and write your own nodes or code.



## Fuse

The schedule of helmut.cloud. (Every brain needs a schedule, right?) Fuse schedules and times regular workflows in the manner of a cronjob-manager. It introduces a way to do regular tasks in software that is missing this feature. Backups, data syncs, watchdogs... Just plan it, forget about it and never forget to do anything anymore.



## The Agent

The hand of helmut.cloud. The helmut.cloud agent is an application installed on workstations or clients that eventually execute the workflows of an organization.

Therefore, every agent needs to be authorized to act for a certain organization with a valid account or token, and the context in which the agent is running needs to be configured beforehand.

This way it is ensured that an agent only executes workflows that it is assigned to and authorized for.
