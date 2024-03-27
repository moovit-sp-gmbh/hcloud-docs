# Docker

The HCloud Docker agents log can be retrieved like any container log in Docker.

Type

```sh
sudo docker stats
```

to get a list of all your containers, then pick the name of the client container which you want to read the logfiles of.

Alternatively, search for a string to reduce the number of line output and get only lines with the hcloud-string in it.

```sh
sudo docker stats | grep -i hcloud
```

Copy the name of the agents container affected and type

```sh
sudo docker logs hcloudagentcontainername
```

to retrieve the logs, or write them into a file like this:

<pre class="language-sh"><code class="lang-sh"><strong>sudo docker logs hcloudagentcontainername > /path/to/mylogfile.log
</strong></code></pre>

Like with any container, you can use third party tools to automatically collect logs and process or visualize information from your agents that are running as containers. You can also use helmut.cloud to collect and distribute logfiles to a location of your liking.
