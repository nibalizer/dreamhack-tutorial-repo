# Extend your Livestream with Open Source 

You can follow along with these instructions. The workshop leader will demonstrate for you. You can put your hand up and a TA will help you with your issue.

Credentials - https://gist.github.com/nibalizer/404notfound

Steps:


1) clone the example app:  

```
git clone https://github.com/ibm-dev/watson-twitch-tone-analysis
```

2) Check out the correct branch `dreamhack`

```
cd watson-twitch-tone-analysis
git checkout dreamhack
```

3) Create dir `secrets` and file `config.json` inside . Put the following text in `config.json`

```
{
"watson": {
  "version_date": "2016-05-19",
  "new": {
    "apikey": "some-url",
    "url": "some-url"
  }
},

"twitch_identity": {
  "username": "MyTwitchUsername1337",
  "password": "oauth:abs8uftnibeSOMETOKEN"
},

"twitch_channels": ["channel1", "channel2"]

}
```


4) Get a twitch chat api key: https://twitchapps.com/tmi/

5) Get watson tone password from "Credentials" above: https://gist.github.com/nibalizer/404notfound

6) Fill out content in `config.json`

* Note for the Watson section: Credentials are pulled from the Credentials section above
* Note for the Twitch section: usernames is your 
* Note for the Twtich Channels section: leave this as-is, we'll set up channels later


7) Install dependencies

```
npm install
```

8) Start the app


```
npm start
```


9) Poke

http://localhost:3000
http://localhost:3000/anger


1) Sign up for IBM Cloud: https://cloud.ibm.com/registration

2) Install ibmcloud utils: https://cloud.ibm.com/docs/cli?topic=cloud-cli-install-ibmcloud-cli

3) Setup cf

```
ibmcloud target --cf
```

4) Create an app definiton file `manifest.yml`

```
---
applications:
 - name: TwitchToneCF
   random-route: true
   memory: 256M
```


5) Start app

```
ibmcloud cf push
```


6) You'll get a URL to hit: hit it!

7) The app has a five minute timeout built-in. (index.js, line 82) Modify this so it doesn't do a timeout then redeploy the app!

```
vim index.js
```

```
ibmcloud cf push
```

8) Right now you're using my Watson Tone Analysis service. Go to ibmcloud.com, create your own watson service, and start using that in the app.


* https://github.com/nibalizer/Twitch-Picks-CSGO
* https://github.com/nibalizer/obs-scripts-examples/blob/master/chat-votes-camera.py
* https://github.com/nibalizer/obs-scripts-examples/blob/master/sc2client.py


Credentials - https://gist.github.com/nibalizer/404notfound

References - https://spencerkrum.com/posts/open_source_streaming_references/
