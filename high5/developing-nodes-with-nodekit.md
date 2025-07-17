# Developing nodes with NodeKit

## Getting Started Guide

This guide will take you step-by-step through the process of building and publishing your first node catalog, from start to finish.

### **What is NodeKit?**

NodeKit provides all the essential tooling, UI components, helper classes, and documentation needed to develop, test, and distribute node catalogs in [helmut.cloud](http://helmut.cloud).&#x20;

You can create nodes using TypeScript, leveraging the ever-growing universe of Node.js packages to develop sophisticated and feature-rich node catalogs.&#x20;

NodeKit simplifies the process of building, testing, and publishing your node catalog, making it readily available for use within the High5 Stream Designer Studio

#### Prerequisites:

* A GitHub account
* A [helmut.cloud](http://helmut.cloud/) account
* The [helmut.cloud](http://helmut.cloud/) agent version 1.2.0 or newer installed and running

#### Recommendations:

* Visual Studio Code

### 1. Create a new repo from the wave-node-catalog-blueprint template:

First things first, let’s create a new repo in your GitHub account using the official Wave Node Catalog Blueprint. This blueprint is packed with goodies: sample code, GitHub Actions for building and publishing, linting rules, and much more. 🎩✨

1. Head over to [wave-nodes-catalog-blueprint](https://github.com/moovit-sp-gmbh/wave-nodes-catalog-blueprint) on GitHub, click "**Use this template**," then "**Create a new repository**."

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/9c31f875-bffe-4b60-ae28-01c362c8b321/Screen%20Shot%202024-09-06%20at%2009.20.56.png" alt=""><figcaption></figcaption></figure>

2. On the "**Create new repository**" page, ensure "**Repository template**" is set to **"moovit-sp-gmbg/wave-nodes-catalog-blueprint"**, and set the owner to your account.

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/3b188b11-ff2a-4b22-adc0-62cb932e2eb5/Screen%20Shot%202024-09-06%20at%2009.21.25.png" alt=""><figcaption></figcaption></figure>

3. Give your repository a name, set the visibility (public or private), and hit "**Create repository**"

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/3808d6f0-9d9b-4a7b-86fe-ec32da3d045b/Screen%20Shot%202024-09-06%20at%2009.21.49.png" alt=""><figcaption></figcaption></figure>

4. Once your repo is ready, click the "Code" dropdown and copy the HTTPS link. You'll need it for the next step

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/a712a550-0f5f-4715-af3f-d1ee58e06594/Screen%20Shot%202024-09-06%20at%2009.22.41.png" alt=""><figcaption></figcaption></figure>

### 2. Code and Test:

1. Now it's time to dive into the fun part, coding! 🧑‍💻 Grab the HTTPS link from your new repo, open the terminal in VSCode, and paste the link to clone the repo to your local machine.

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/3145929a-634c-44a9-a32d-cac71cdc8983/Screenshot%202024-09-06%20at%2009.23.36.png" alt=""><figcaption></figcaption></figure>

2. Once cloned, open the folder in Visual Studio Code and run: `npm i` . This will install all project dependencies from `package.json`

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/e2697ae6-4fa1-4a8b-984e-88e344efd779/Screenshot%202024-09-06%20at%2009.25.39.png" alt=""><figcaption></figcaption></figure>

3. Once that’s done, navigate to the "**lib**" folder, expand the "**nodes**" folder, and create your first `node.ts` file. For a solid starting point, check out `HttpClient.ts` . This node serves as a blueprint for building new nodes. In this file, you can explore how to use helper classes, read inputs, set outputs, and understand how the node specification works, along with much more.

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/1b3b6330-9800-4442-856d-19803ed07ecb/Screenshot%202024-09-06%20at%2009.32.11.png" alt=""><figcaption></figcaption></figure>

4. Once you’ve finished coding your nodes, open the `index.ts` file and import all the nodes you’ve created at the top of the file. Here’s an example:

```typescript
import Demo from "./lib/nodes/Demo";
```

5. Now it’s time to configure the catalog instance. You’ll need to provide the following details:

* **Name:** The catalog’s name, e.g., "**Microsoft Teams**"- **Description:** A brief description, e.g., "**Nodes to send messages in Microsoft Teams**"
* **Logo:** A `.webp` logo file (max size X by Y) hosted at a publicly accessible URL.&#x20;
* **Wave Engine Version:** Specify the minimum version of the Wave Engine required to run your catalog.&#x20;

Finally, add the nodes that should be bundled in your node catalog.&#x20;

Here's an example:

```typescript
export default new Catalog(
  "Demo Catalog",
  "This is my first external node catalog",
  "https://app.helmut.cloud/img/logo_white.webp",
  "1.0.0",
  Demo,
  Demo2
);
```

### 3. Test your node:

Testing your nodes couldn’t be easier, and the best part? You don’t even need to publish them first. Pretty awesome, right? 😎\
\
Once you’re happy with your code, just follow these steps:\


1. Open a terminal in VSCode and run: `npm i`
2. Next, link your node to the helmut.cloud agent by running:: `npm run link` . This command automatically links the helmut.cloud agent to the local file path where your node code lives on your local machine.
3. Finally, generate the specification for your node by running:: `npm run spec -- <name-of-your-node>` . This will output the full spec for your node directly in the terminal.

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/9f411943-f549-4823-822b-d1064ff2e915/Screenshot%202024-09-06%20at%2023.12.47.png" alt=""><figcaption></figcaption></figure>

3. Copy the JSON output, hop over to the Stream Designer Studio. Press`Ctrl + K` (Windows) or `Cmd + K` (Mac) to bring up the command palette. Type ‘**Import node specification**’ into the search bar, select the option, and press `Return` to open it.

<figure><img src="../.gitbook/assets/Screen Shot 2025-07-17 at 09.53.26.png" alt=""><figcaption></figcaption></figure>

4. Paste the JSON into the input field of the **'Import dev node specification**' window and press `Return`. The node will be added to your canvas, ready for testing.

<figure><img src="../.gitbook/assets/Screen Shot 2025-07-17 at 09.53.47.png" alt=""><figcaption></figcaption></figure>

### 4 Debugging your node's code:

Found a bug or just want to step through your code? We've got you covered!

1. Start by opening a JavaScript Debug Terminal in VSCode.
2. If the helmut.cloud agent is running, stop it first, then run `npm run debug` to launch it in debug mode.
3. Then, run `npm run link` to link your [helmut.cloud](http://helmut.cloud) agent to your local node file path.
4. Set one or more breakpoints in your code where you want execution to pause.
5. Execute the stream, and the debugger will stop at your breakpoints, allowing you to inspect and step through your node code.

### 5. Configure the s3 storage:

The repo comes pre-configured with a GitHub Action that automates building and publishing your node catalog to S3 storage. You'll just need to configure a few properties:

* **S3 Bucket Endpoint**: The endpoint of your S3 bucket.
* **Bucket Name**: The name of your S3 bucket.
* **Public Endpoint**: The public URL where your S3 bucket is accessible.
* **Region**: The region where your S3 bucket is hosted.
* **Access Key ID**: Your S3 access key ID.
* **Access Key Secret**: The secret associated with your access key.
* **Destination Directory**: The folder on your S3 bucket where the node catalog will be stored.

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/edabb7e5-6327-456c-90c0-a06bbcd4028f/Screenshot%202024-09-06%20at%2014.12.25.png" alt=""><figcaption></figcaption></figure>

### 6. Deploy

Now that your node is ready, it’s time to push it!&#x20;

1. Open your terminal in VS Code and stage your changes with: `git add .`
2. Commit your changes with: `git commit -a -m "commit message"`
3. Tag your release: `git tag vx.x.x`
4. Finally, push your local commits: `git push origin vx.x.x`&#x20;

Once pushed head to GitHub, open the "**Actions**" tab, and expand the "_**Upload catalog to S3**_" workflow

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/eee7914d-cd85-4d0d-80db-6755ef581434/Screen%20Shot%202024-09-06%20at%2014.22.39.png" alt=""><figcaption></figcaption></figure>

Expand the "**Print catalog registry URL**" section and copy the URL

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/604928e0-346e-4c8d-8ea2-b1d8dd927c84/Screen%20Shot%202024-09-06%20at%2014.23.09.png" alt=""><figcaption></figcaption></figure>

### 7. Import the node catalog in Stream Designer Studio:

Now that your catalog is built and you’ve got the public URL, it’s time to import it into Stream Designer Studio.

1. Go to the node panel, click "**Manage node catalogs**"

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/a34d38c2-a003-4033-981e-216abecc0f4e/Screen%20Shot%202024-09-06%20at%2023.19.50.png" alt=""><figcaption></figcaption></figure>

2. On the "**Manage node catalog**" screen, click "**Add external catalog**"

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/bb021253-d8b9-400a-aef1-728f89b2783b/Screen%20Shot%202024-09-06%20at%2023.19.56.png" alt=""><figcaption></figcaption></figure>

3. Paste the URL, and hit "**`Save`**"

<figure><img src="https://t2570196.p.clickup-attachments.com/t2570196/35b470ee-f806-484a-a26e-881ca00d7506/Screen%20Shot%202024-09-06%20at%2023.20.00.png" alt=""><figcaption></figcaption></figure>

Congratulations! 🎉 You've now successfully developed, tested, built, and published your node catalog!
