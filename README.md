# HONK

## HONK

HONK

## Process

* set up empty repo
* npm init
* npm i slack, dotenv
* create channel called untitled-goose-channel
* Create your app (must be an app that is a bot user, not the bots integration, this will be deprecated) https://api.slack.com/apps?new_app=1
* name it honkbot (or whatever, but we're going to use honkbot), and choose the workspace you want to install it to
* before you install it to your workspace, you have to add a feature - let's add bot user
* you'll go to your apps settings page, you need to install it into your workspace
* https://api.slack.com/bot-users#creating-bot-user
* you need an endpoint for the Events API to hit - let's get a basic Express server on Netlify https://github.com/neverendingqs/netlify-express (hit deploy)
* name your repo honkbot-server or something
* curl https://quizzical-ardinghelli-c131b8.netlify.com/.netlify/functions/server, see the response
* go into your honktbot server repo and add the honk endpoint POST, because Slack Events API wants to POST you with a 'challenge' parameter and you have to respond (req.body.challenge) using res.json https://api.slack.com/events/url_verification
* add the url now and it should work
* let's add some bot events to subscribe to: message.channels and member_joined_channel
* reinstall the app



Helpful documentation

* channels.info method on Slack Docs https://api.slack.com/methods/channels.info
* incoming webhooks to send info into Slack https://api.slack.com/incoming-webhooks
* outgoing webhooks for listening for a trigger https://api.slack.com/custom-integrations/outgoing-webhooks
* Creating a bot user https://api.slack.com/bot-users#creating-bot-user
* Responding in thread https://api.slack.com/methods/chat.postMessage#threads_and_replies
* https://app.netlify.com/sites/quizzical-ardinghelli-c131b8/overview