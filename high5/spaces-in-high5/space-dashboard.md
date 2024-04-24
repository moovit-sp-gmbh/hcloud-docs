# Space dashboard

The spaces dashboard shows stream executions that have been happening in this very High5 space.

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



To view all jobs of your organizations High5, look at the [organization dashboard](../organization-dashboard.md).
