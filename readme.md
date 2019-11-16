# Extend your Livestream with Open Source 



* https://github.com/nibalizer/Twitch-Picks-CSGO
* https://github.com/nibalizer/obs-scripts-examples/blob/master/chat-votes-camera.py
* https://github.com/nibalizer/obs-scripts-examples/blob/master/sc2client.py


Credentials - https://gist.github.com/nibalizer/4b3c1e705a020166c7ec3202eccae7f4

References - https://spencerkrum.com/posts/open_source_streaming_references/



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

3) Create dir `secrets` and file `config.json`

4) Get a twitch chat api key: https://twitchapps.com/tmi/

5) Get watson tone password from "Credentials" above: https://gist.github.com/nibalizer/4b3c1e705a020166c7ec3202eccae7f4

6) Fill out content in `config.json`


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


7) Start the app


```
npm start
```


8) Poke

http://localhost:3000
http://localhost:3000/anger


1) Sign up for IBM Cloud: https://cloud.ibm.com/registration

2) Install ibmcloud utils: https://cloud.ibm.com/docs/cli?topic=cloud-cli-install-ibmcloud-cli

3) Setup cf

```
ibmcloud target
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
