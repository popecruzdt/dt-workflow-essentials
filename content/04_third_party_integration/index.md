## Third Party Integration

Goal: When a Davis problem event is triggered, send a problem summary as a Slack message to a chosen Slack channel.

- Event Trigger
    * Trigger Workflow when a Davis problem event is detected
    * Events are filtered on the type of event, based on the previous exercise
- Slack for Workflows
    * Third party integration is typically accomplished with Workflow Apps
    * The Slack for Workflows App provides an easy-to-use mechanism for sending messages to a Slack environment containing the data and context from Dynatrace
    * Leverage Jinja expressions to access Workflow action results and implement logic

### Slack for Workflows
Your Dynatrace environment can integrate with a Slack workspace using Slack for Workflows. You can automate sending messages to Slack based on the events and schedules defined for your workflow.

[Slack for Workflows Documentation](https://docs.dynatrace.com/docs/platform-modules/automations/workflows/actions/slack)

Setting up the Slack integration is straight forward and well documented.  In the interest of time and simplicity, the Slack integration has already been configured for this lab.