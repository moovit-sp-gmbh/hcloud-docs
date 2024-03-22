# 🔥 Step 5: Run your first workflow

The moment has come, tension rises: You can now use the webhook and trigger it with CURL from a terminal.

* Open a terminal (and check if you have CURL installed)
* Copy the webhooks URL from the your spaces webhooks-section by clicking the little pasteboard icon next to the name
* Enter this into your terminal and replace the placeholder with your link:

```bash
curl POST "https://app.helmut.cloud/api/high5/v1/org/MyOrganization/placeholder" \
-H "knockknock:itsme" -H "content-type:application/json" -d "{}"
```

If your hello-world website opens in your browser now: Congratulations, you made it!

You can later observe if your webhook accepted the trigger by clicking on the name in the webhooks-section and view the logs. If you get a 204, this is fine, because we did not send any content in the payload. Click on the entry to view some details about the call, like headers and payload or response.
