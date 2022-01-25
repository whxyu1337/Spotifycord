# Spotifycord
A code that allows you to get custom spotify rich presence!

----

The [index.js](https://github.com/SealedSaucer/Spotifycord/blob/main/index.js) is the main file. [server.js](https://github.com/SealedSaucer/Spotifycord/blob/main/server.js) prevents your repl from going to sleep. (If you have a replit hacker plan, then you can delete [this file](https://github.com/SealedSaucer/Spotifycord/blob/main/server.js) and paste this code inside the [index.js](https://github.com/SealedSaucer/Spotifycord/blob/main/index.js) file : 

</br>

```js
const dotenv = require('dotenv');
const TOKEN = (process.env.TOKEN);
const { Client } = require('discord.js-selfbot-v11')
let rpcGenerator = require("discordrpcgenerator")
const client = new Client();

let CLIENT_ID = "CLIENT_ID"
let IMAGE = "IMAGE_NAME"
let SONG = "SONG_NAME"
let ARTIST = "ARTIST"

client.on("ready", () => {
    rpcGenerator.getRpcImage(CLIENT_ID, IMAGE)
    .then(image => {
    let presence = rpcGenerator.createSpotifyRpc(client)
    .setApplicationId(CLIENT_ID)
    .setAssetsLargeImage(image.id)
    .setDetails(SONG)
    .setState(ARTIST)
    client.user.setPresence(presence.toDiscord())
    }).catch(console.error)
  console.log(`${client.user.username} Successfully Logged in!`)
})

client.login(TOKEN);
```

This Code is from [this tutorial](https://youtube.com). If you have any doubts regarding this, feel free to [contact me](https://dsc.gg/phantom).

**DO NOT GIVE YOUR TOKEN TO OTHERS!**

Use [uptimerobot.com](https://uptimerobot.com) to make your repl online 24/7.

</br>

> ⭐ Feel free to Star the Repository if this helped you! ;)

----

> Spotifycord © 2022 by SealedSaucer is licensed under Attribution 4.0 International 
