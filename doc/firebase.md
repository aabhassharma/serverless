## Hosting the sh*t out of your static website

So you want to host a static website. It would be awesome if you could
just throw it in to a S3/GCS bucket, and share that URL. While you could do
that and get most of the way there, there's no good way to do end to end
HTTPS with that approach. Sure, you could use Cloudflare and get HTTPS for free,
or you could Firebase.

### Getting Started
Yuck. Node. On my computer. Yuck.

1. Install node, then install firebase-tools
```
curl "https://nodejs.org/dist/latest/node-${VERSION:-$(wget -qO- https://nodejs.org/dist/latest/ | sed -nE 's|.*>node-(.*)\.pkg</a>.*|\1|p')}.pkg" > "$HOME/Downloads/node-latest.pkg" && sudo installer -store -pkg "$HOME/Downloads/node-latest.pkg" -target "/"
npm install -g firebase-tools
```

2. Login to firebase (which is a great flow btw)
```
firebase login
```

3. Follow the amazing graphics with init-ing your project
```
firebase init
```
Follow the onscreen instructions, and we're good!

### Build a guest book
Heads up, I'm horrible at HTML. Or Javascript. Or pretty much anything to do with
websites. So, this is simple. And it works.

Put the HTML content for your guestbook in the [index.html](../public/index.html)
that was created when you did the firebase init. 
