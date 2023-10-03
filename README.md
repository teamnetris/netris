Netris [](https://npmjs.com/package/netris)
====

A JavaScript library for interfacing with Discord API.

Installing
----------

You will need NodeJS 18+ If you need voice support you will also need Python 2.7 and a C++ compiler.

```
npm install --no-optional netris
```

If you need voice support, remove the `--no-optional`.

Ping Pong Example
-----------------

```js
const { Client } = require("netris");

// Replace TOKEN with your bot token
const client = new Client("TOKEN", {
    intents: [
        "guildMessages"
    ]
});

client.on("ready", () => { // When the bot is ready
    console.log("Client is ready!"); // Log "Client is ready!"
});

client.on("error", (error) => {
  console.error(error); // or your preferred logger
});

client.on("messageCreate", (message) => { // When a message is created
    if(message.content === "!ping") { // If the message content is "!ping"
        message.channel.createMessage("Pong 🏓");
        // Send a message in the same channel with "Pong 🏓"
    } else if(message.content === "!pong") { // Otherwise, if the message is "!pong"
        message.channel.createMessage("Ping 🏓");
        // Respond with "Ping 🏓"
    }
});

client.connect(); // Get the bot to connect to Discord
```

More examples can be found in [the examples folder](https://github.com/teamnetris/netris/tree/master/examples).

License
-------

Refer to the [LICENSE](LICENSE) file.