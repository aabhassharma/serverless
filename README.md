# serverless
Seeing how far I can take the whole "serverless" magic

## Server-what?
You've probably heard about this trend now. Servers are so last decade. The
future (ok I'm exaggerating a little) is all about being serverless.

No more managing servers, or provisioning, or making sure that you're utilizing
the cores on your provisioned machines to the full.

## The plan

Use as many off the shelf tools to make a simple guest book where people can
enter their name, and a cute message (although knowing the harsh internet it'll
turn in to a troll fest in no time). Don't involve a server, ever.

### Static Content Hosting
For hosting the static content, I chose Firebase hosting. I would have loved
to simply use GCS, and not involve Firebase at all, but GCS doesn't let one
serve HTTPS end to end for custom domains, and we're not trying to have a less
than fort knox secure experience here, because guest books are important.

[This](./doc/firebase.md) document will walk you through setting up a static website with
Firebase hosting, and serve it on your custom domain with end to end HTTPS.

Note: I am not a Javascript developer, this is my first time using Node, and
my whole goal was to minimize the amount of Javascript or Node things I have to
do (and use Python instead).

### Functions, Or You Know, Real Work
Google Cloud Functions! For actually doing the "work" on this website, I chose
Google Cloud Functions. Using app engine to actually do the work would be
cheating, and Cloud Functions are serverless, so perfect fit!

[This](./doc/cloudfunctions.md) document will walk you through setting up a cloud function that
accepts the names for the guest book, and the message, and stores them.

### Edge computing
I couldn't not talk about the other buzz phrase - "Edge Computing". Having been
a long time Cloudflare customer, I actually helped them Beta Test and launch
Cloudflare workers, an awesome solution for "edge computing", taking this serverless
stuff to a whole other level. Unfortunately, for the purpose of this project,
I can't afford to pay for Cloudflare or for Workers, so you'll just need to imagine
that I used workers to do something funky, and I'll explain workers and some
examples in [this](bleh) doc.
[Here's](https://globenewswire.com/news-release/2018/03/13/1421367/0/en/Cloudflare-Workers-Opens-Edge-Computing-to-Everyone.html) a fun news release about me using workers in the mean time ;)
