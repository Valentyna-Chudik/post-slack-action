# GitHub Action: Post Slack Message (Push, Pull Request Git Event)

Inspired by [this github action](https://github.com/alejandrogonzalez3/post-slack-action).

This GitHub Action send an event notification to a specific Slack channel whenever a new PR is created or new changes are pushed to the main branch.

### Inputs

#### Required

- `event`: Event to notify
- `job-status`: Specifies the final job state
- `slack-bot-token`: Bot token chosen to "write" in the channel
- `channel`: Channel where the message will be sended

### Example Usage

Create a workflow yaml file (for e.g. `.github/workflows/slack.yml`).

```
- name: Slack message Action
    uses: ./ # Uses an action in the root directory
    id: Slack Action
    with:
        event: ${{ toJson(github.event) }}
        job-status: ${{ job.status }}
        slack-bot-token: ${{ secrets.SLACK_BOT_TOKEN }}
        channel: pr
```
