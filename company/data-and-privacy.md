# Data and Privacy

### You own your data

Everything you log to Weights & Biases is yours, including your training data, code, configuration and hyperparameters, output metrics, analysis, and saved model files. You can choose to log, export, publish, or delete any of these. We collect aggregate statistics across our users to improve our product— we might do a database query to count how many users have uploaded a requirements.txt that includes a specific library to help decide if we want to do a first class integration with that library. We treat your private data, source code, or trade secrets as confidential and private, as consistent with our [Terms of Service](https://www.wandb.com/terms) and [Privacy Policy](https://www.wandb.com/privacy).‌

### On-prem and private cloud

We follow industry best practices for security and encryption in our cloud-hosted service. We also offer [private cloud and on-prem installations](../self-hosted/) for enterprise customers. [Contact us](getting-help.md) to learn about options for your business.

For personal use, we have a [local Docker installation](../self-hosted/local.md) that you can run on your own machine.‌

### Project privacy and teams

By default Weights & Biases projects are private, which means other users won’t be able to view your work. You can edit this default on your [settings page](https://app.wandb.ai/settings). You can choose to share your results with others by making your project public or creating a team to share private projects with specific collaborators. Teams are a premium feature for companies. Learn more on our [pricing page](https://www.wandb.com/pricing).‌

To support the ML ecosystem, we offer free private teams to academics and open source projects. Sign up for an account and then contact us via [this form](https://www.wandb.com/academic) to request a free private team.

### Code saving

By default, we only pick up the latest git SHA for your code. You can optionally turn on code saving features— this will enable a code comparison panel and tab in the UI to see the version of the code that ran your run. You can turn on code saving in your [settings page](https://app.wandb.ai/settings).

![](../.gitbook/assets/project-defaults.png)

### Exporting data

You can download data saved with Weights & Biases using our [export API](../library/api/). We want to make it easy to do custom analysis in notebooks, back up your data if you'd like to have a local copy, or plug your saved logs into other tools in your ML workflow.

