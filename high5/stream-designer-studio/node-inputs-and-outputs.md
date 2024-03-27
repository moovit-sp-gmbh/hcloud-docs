---
description: Sharing payloads or results between nodes
---

# Node inputs and outputs

To input a payload that is being delivered to the stream (for example from a webhook), use the wildcard \{{payload.data\}} in a nodes input field. It will be resolved with the payload sent to the event /stream.

To read a nodes result, you will need its id and you need to know the nodes outputs, that are documented here or visible in the debugger.\


If you want to read stderr output from the MacOS Command Runner action, you would build a wildcard as follows:

```
// {{output.nodeid.nameofoutput}
```

Or more practical: If you wanted to read stderr output from the MacOS Command Runner action, you would build a wildcard as follows:

```
// {{output.64d3482f-3151-4615-ah29-1a8d2d1cf84b.stdout}}
```
