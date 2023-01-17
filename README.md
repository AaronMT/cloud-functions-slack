# cloud-functions-slack

A Cloud Function to post Firebase Test Lab results to Slack

Largely borrowed from: https://github.com/firebase/functions-samples/tree/main/testlab-to-slack

1. Clone or download this repo and open the `cloud-functions-slack`
   directory.
2. You must have the Firebase CLI installed. If you don't have it install it
   with `npm install -g firebase-tools` and then configure it with
   `firebase login`.
3. Configure the CLI locally by using `firebase use --add` and select your
   project in the list.
4. Install Cloud Functions dependencies locally by running:
   `cd functions; npm install; cd -`
5. Set the following environment variables so that the function can authenticate with Slack and post to the correct room:
   ```firebase functions:config:set slack.webhook_url="YOUR_SLACK_WEBHOOK_URL"```

## Deploy and test

1.  Deploy your function using `firebase deploy --only functions`
2.  Navigate to the
    [Test Lab](https://console.firebase.google.com/u/0/project/_/testlab/histories)
    section of the Firebase Console and start a test.
1.  Once the test finishes running,
    [view the functions logs](https://console.firebase.google.com/u/0/project/_/functions/logs?severity=DEBUG)
    for your project, and check that the test run status was logged.

## Example output
`TEST matrix-2pwpy02hkp9wc (created at 2022-09-26T00:25:58.392882Z): FINISHED. SUCCESS`
