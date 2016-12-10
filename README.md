# ex_mustang

> A simple, clueless bot

![Mustang](images/mustang.jpg)

ExMustang is a bot for Slack written in Elixir.

_Warning: This is a work in progress._

![Example](images/example.png)

### Setup

Create a Slack bot user from [here](https://my.slack.com/services/new/bot). You will receive an API token you can use. Set the `SLACK_API_TOKEN` environment variable and you should be good to go.

You can run this bot as below:

```shell
export SLACK_API_TOKEN="<SLACK_API_TOKEN>"
mix run --no-halt
```

A sample runner configuration looks like below:

```shell
export SLACK_API_TOKEN="<SLACK_API_TOKEN<"
export GITHUB_TOKEN="<GITHUB_TOKEN>"
export GOOGLE_API_KEY="<GOOGLE_API_KEY>"
export STANDUP_CHANNEL="G02KTGABR"
export GH_CHANNEL="G02KTGABR"
```

### Scheduled Notifications

#### Github Pull Requests Watcher

You can configure github token by setting `GITHUB_TOKEN`. Also, you can pass list of repos to watch by updating [config](config/config.exs#L11-L17). There are bunch of other stuffs you can configure such as schedule (which follows cron format), slack channel and thresholds.

#### Standup Reminder

The standup reminder reminds us when its standup time. Our nature is that we either forget track of time or are too lazy to remember about it. This does not make you better at attending standup but is more of a satire for us. You can configure message and other bunch of stuffs on [config](config/config.exs#L5-L9)

### Responders

Currently, there are three responders and these should ideally work with any Hedwig adapters:

- `ExMustang.Responders.GMap` - gives you google maps search result for your search queries.
- `ExMustang.Responders.Quote` - gives you random funny quote
- `ExMustang.Responders.Slap` - slaps another user
- `ExMustang.Responders.Time` - gives time on given timezone (without timezone, uses local timezone of machine ExMustang is running on)

For Google Maps search, you have to set `GOOGLE_API_KEY` which has access to call google places api.

```shell
mustang help - Displays all of the help commands that mustang knows about.
mustang help <query> - Displays all help commands that match <query>.
gmap <search_term> - Replies with the information from google places/maps.
quote - Replies with a random quote.
slap - Slaps the user. Format: slap <username> | me
```

### About Mustang

Mustang (pronounced like `moostang` not like the `Ford Mustang`; I don't know phonetics) is my best friend whom I had to leave back in Nepal. After surviving [April 2015 Earthquake](https://en.wikipedia.org/wiki/April_2015_Nepal_earthquake), we lived together for a while and I had to leave him back in Nepal. Below is the pic post-earthquake.

![Mustang and Me](images/me_mustang.jpg)
