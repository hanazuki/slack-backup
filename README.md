# slack-backup-files

Back up the files uploaded to your Slack workspace in case of disaster and in case of running out of your free-plan storage :slightly_smiling_face:

## Usage

```
# Back up each file on Slack to the local storage and delete it if it was uploaded more than 30 days ago,
# and delete it even if the backup was failed when the file is more than 45 days old.
# --dryrun instructs not to actually backup or delete any files.
export SLACK_TOKEN=xoxp-XXXXXXXXXX-...
slack-bakcup-files --backup=/path/to/backup/file --delete-after=30 --force-delete-after=45 --dryrun
```

- Only files uploaded to a public channel (not a private group or direct message) will be backed up.
- Any files pinned to a channel will be kept on Slack.
- Only files accessible using the `SLACK_TOKEN` will be backed up and deleted.
  So use a token for a workspace admin if you want to delete files, and note that any file uploaded to a private channel that the token owner does not belong to cannot be deleted.

