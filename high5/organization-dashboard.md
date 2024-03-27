# Organization dashboard

The organization-wide dashboard shows you all stream executions that have been happening in the High5 instance of the organization you are working in.

It can

* Filter jobs to include / exclude / contain job properties like name, creator, status etc
* Cancel queued jobs
* Delete queued jobs
* Restart jobs that were canceled or failed
* Delete completed jobs
* Change the priority of a queued job (when authorized)

Examples:

To look for all executions made before March 23 2024, build a filter like this:

```
Field: Created        Comparator: LESS_THAN        Value: YourDateFormat 
```

To search for a stream that contains a string like "Error":

```
Field: Message        Comparator: CONTAINS         Value: Error 
```

Click add and the filter will be applied.



In contrast to the organization-wide dashboard, there is a [dashboard for every single space](spaces-in-high5/space-dashboard.md) as well. It works the same way, but filters to the spaces jobs by default.
