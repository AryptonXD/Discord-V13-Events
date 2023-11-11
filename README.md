Discord.js v13 Events
---
An overview of all events in Discord.js v13 with examples.

📢 | Last updated: 11th November 2023

ℹ️ | `client` references to your client instance.

ℹ️ | The v14 overview can be found [here](https://github.com/AryptonXD/Discord-V14-Events).

### Events

<details>
<summary>List of events in this overview</summary>
<br>

- [apiRequest](#apirequest)
- [apiResponse](#apiresponse)
- [applicationCommandCreate](#applicationcommandcreate)
- [applicationCommandDelete](#applicationcommanddelete)
- [applicationCommandUpdate](#applicationcommandupdate)
- [channelCreate](#channelcreate)
- [channelDelete](#channeldelete)
- [channelPinsUpdate](#channelpinsupdate)
- [channelUpdate](#channelupdate)
- [debug](#debug)
- [emojiCreate](#emojicreate)
- [emojiDelete](#emojidelete)
- [emojiUpdate](#emojiupdate)
- [error](#error)
- [guildBanAdd](#guildbanadd)
- [guildBanRemove](#guildbanremove)
- [guildCreate](#guildcreate)
- [guildDelete](#guilddelete)
- [guildIntegrationsUpdate](#guildintegrationsupdate)
- [guildMemberAdd](#guildmemberadd)
- [guildMemberAvailable](#guildmemberavailable)
- [guildMemberRemove](#guildmemberremove)
- [guildMembersChunk](#guildmemberschunk)
- [guildMemberUpdate](#guildmemberupdate)
- [guildScheduledEventCreate](#guildscheduledeventcreate)
- [guildScheduledEventDelete](#guildscheduledeventdelete)
- [guildScheduledEventUpdate](#guildscheduledeventupdate)
- [guildScheduledEventUserAdd](#guildscheduledeventuseradd)
- [guildScheduledEventUserRemove](#guildscheduledeventuserremove)
- [guildUnavailable](#guildunavailable)
- [guildUpdate](#guildupdate)
- [interaction](#interaction)
- [interactionCreate](#interactioncreate)
- [invalidated](#invalidated)
- [invalidRequestWarning](#invalidrequestwarning)
- [inviteCreate](#invitecreate)
- [inviteDelete](#invitedelete)
- [message](#message)
- [messageCreate](#messagecreate)
- [messageDelete](#messagedelete)
- [messageDeleteBulk](#messagedeletebulk)
- [messageReactionAdd](#messagereactionadd)
- [messageReactionRemove](#messagereactionremove)
- [messageReactionRemoveAll](#messagereactionremoveall)
- [messageReactionRemoveEmoji](#messagereactionremoveemoji)
- [messageUpdate](#messageupdate)
- [presenceUpdate](#presenceupdate)
- [rateLimit](#ratelimit)
- [ready](#ready)
- [roleCreate](#rolecreate)
- [roleDelete](#roledelete)
- [roleUpdate](#roleupdate)
- [shardDisconnect](#sharddisconnect)
- [shardError](#sharderror)
- [shardReady](#shardready)
- [shardReconnecting](#shardreconnecting)
- [shardResume](#shardresume)
- [stageInstanceCreate](#stageinstancecreate)
- [stageInstanceDelete](#stageinstancedelete)
- [stageInstanceUpdate](#stageinstanceupdate)
- [stickerCreate](#stickercreate)
- [stickerDelete](#stickerdelete)
- [stickerUpdate](#stickerupdate)
- [threadCreate](#threadcreate)
- [threadDelete](#threaddelete)
- [threadListSync](#threadlistsync)
- [threadMembersUpdate](#threadmembersupdate)
- [threadUpdate](#threadupdate)
- [typingStart](#typingstart)
- [userUpdate](#userupdate)
- [voiceStateUpdate](#voicestateupdate)
- [warn](#warn)
- [webhookUpdate](#webhookupdate)
</details>

---

### ***apiRequest***

Emitted before every API request. This event can emit several times for the same request, e.g. when hitting a rate limit.

| Parameter | Type                                                                       | Description                          |
| --------- | -------------------------------------------------------------------------- | ------------------------------------ |
| request   | [APIRequest](https://discord.js.org/#/docs/main/stable/typedef/APIRequest) | The request that is about to be send |

```js
client.on('apiRequest', (request) => {
    console.log(`apiRequest: ${request}`);
});
```

### ***apiResponse***

Emitted after every API request has received a response. This event does not necessarily correlate to completion of the request, e.g. when hitting a rate limit.

| Parameter | Type                                                                       | Description                                |
| --------- | -------------------------------------------------------------------------- | ------------------------------------------ |
| request   | [APIRequest](https://discord.js.org/#/docs/main/stable/typedef/APIRequest) | The request that is about to be send       |
| response  | [Response](https://developer.mozilla.org/en-US/docs/Web/API/Response)      | The response received from the Discord API |

```js
client.on('apiResponse', (request, response) => {
    console.log(`apiResponse: ${request} | ${response}`);
});
```

### ***applicationCommandCreate***
> ⚠️ | This event is deprecated, see [this issue](https://github.com/discord/discord-api-docs/issues/3690) for more information.

Emitted when a guild application command is created.

| Parameter | Type                                                                                     | Description                   |
| --------- | ---------------------------------------------------------------------------------------- | ----------------------------- |
| command   | [ApplicationCommand](https://discord.js.org/#/docs/main/stable/class/ApplicationCommand) | The command which was created |

```js
client.on('applicationCommandCreate', (command) => {
    console.log(`applicationCommandCreate: ${command}`);
});
```

### ***applicationCommandDelete***
> ⚠️ | This event is deprecated, see [this issue](https://github.com/discord/discord-api-docs/issues/3690) for more information.

Emitted when a guild application command is deleted.

| Parameter | Type                                                                                     | Description                   |
| --------- | ---------------------------------------------------------------------------------------- | ----------------------------- |
| command   | [ApplicationCommand](https://discord.js.org/#/docs/main/stable/class/ApplicationCommand) | The command which was deleted |

```js
client.on('applicationCommandDelete', (command) => {
    console.log(`applicationCommandDelete: ${command}`);
});
```

### ***applicationCommandUpdate***
> ⚠️ | This event is deprecated, see [this issue](https://github.com/discord/discord-api-docs/issues/3690) for more information.

Emitted when a guild application command is updated.

| Parameter  | Type                                                                                      | Description                   |
| ---------- | ----------------------------------------------------------------------------------------- | ----------------------------- |
| oldCommand | ?[ApplicationCommand](https://discord.js.org/#/docs/main/stable/class/ApplicationCommand) | The command before the update |
| newCommand | [ApplicationCommand](https://discord.js.org/#/docs/main/stable/class/ApplicationCommand)  | The command after the update  |

```js
client.on('applicationCommandUpdated', (oldCommand, newCommand) => {
    console.log(`applicationCommandUpdated: ${oldCommand} | ${newCommand}`);
});
```

### ***channelCreate***

Emitted whenever a guild channel is created.

| Parameter | Type                                                                         | Description                  |
| --------- | ---------------------------------------------------------------------------- | ---------------------------- |
| channel   | [GuildChannel](https://discord.js.org/#/docs/main/stable/class/GuildChannel) | The channel that was created |

```js
client.on('channelCreate', (channel) => {
    console.log(`channelCreate: ${channel}`);
});
```

### ***channelDelete***

Emitted whenever a channel is deleted.

| Parameter | Type                                                                                                                                                   | Description                  |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------- |
| channel   | [DMChannel](https://discord.js.org/#/docs/main/stable/class/DMChannel) or [GuildChannel](https://discord.js.org/#/docs/main/stable/class/GuildChannel) | The channel that was deleted |

```js
client.on('channelDelete', (channel) => {
    console.log(`channelDelete: ${channel}`);
});
```

### ***channelPinsUpdate***

Emitted whenever the pins of a channel are updated. Due to the nature of the WebSocket event, not much information can be provided easily here - you need to manually check the pins yourself.

| Parameter | Type                                                                                          | Description                                  |
| --------- | --------------------------------------------------------------------------------------------- | -------------------------------------------- |
| channel   | [TextBasedChannels](https://discord.js.org/#/docs/main/stable/typedef/TextBasedChannels)     | The channel that the pins update occurred in |
| time      | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | The time of the pins update                  |

```js
client.on('channelPinsUpdate', (channel, time) => {
    console.log(`channelPinsUpdate: ${channel} | ${time}`);
});
```


### ***channelUpdate***

Emitted whenever a channel is updated - e.g. name change, topic change, channel type change.

| Parameter  | Type                                                                                                                                                   | Description                   |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------- |
| oldChannel | [DMChannel](https://discord.js.org/#/docs/main/stable/class/DMChannel) or [GuildChannel](https://discord.js.org/#/docs/main/stable/class/GuildChannel) | The channel before the update |
| newChannel | [DMChannel](https://discord.js.org/#/docs/main/stable/class/DMChannel) or [GuildChannel](https://discord.js.org/#/docs/main/stable/class/GuildChannel) | The channel after the update  |

```js
client.on('channelUpdate', (oldChannel, newChannel) => {
    console.log(`channelUpdate: ${oldChannel} | ${newChannel}`);
});
```

### ***debug***

Emitted for general debugging information.

| Parameter | Type                                                                                              | Description    |
| --------- | ------------------------------------------------------------------------------------------------- | -------------- |
| info      | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | The debug info |

```js
client.on('debug', (debug) => {
    console.log(`debug: ${info}`);
});
```

### ***emojiCreate***

Emitted whenever a custom emoji is created in a guild.

| Parameter | Type                                                                     | Description                |
| --------- | ------------------------------------------------------------------------ | -------------------------- |
| emoji     | [GuildEmoji](https://discord.js.org/#/docs/main/stable/class/GuildEmoji) | The emoji that was created |

```js
client.on('emojiCreate', (emoji) => {
    console.log(`emojiCreate: ${emoji}`);
});
```

### ***emojiDelete***

Emitted whenever a custom emoji is deleted in a guild.

| Parameter | Type                                                                     | Description                |
| --------- | ------------------------------------------------------------------------ | -------------------------- |
| emoji     | [GuildEmoji](https://discord.js.org/#/docs/main/stable/class/GuildEmoji) | The emoji that was deleted |

```js
client.on('emojiDelete', (emoji) => {
    console.log(`emojiDelete: ${emoji}`);
});
```

### ***emojiUpdate***

Emitted whenever a custom emoji is updated in a guild.

| Parameter | Type                                                                     | Description   |
| --------- | ------------------------------------------------------------------------ | ------------- |
| oldEmoji  | [GuildEmoji](https://discord.js.org/#/docs/main/stable/class/GuildEmoji) | The old emoji |
| newEmoji  | [GuildEmoji](https://discord.js.org/#/docs/main/stable/class/GuildEmoji) | The new emoji |

```js
client.on('emojiUpdate', (oldEmoji, newEmoji) => {
    console.log(`emojiUpdate: ${oldEmoji} | ${newEmoji}`);
});
```


### ***error***

Emitted when the client encounters an error.

| Parameter | Type                                                                                            | Description                |
| --------- | ----------------------------------------------------------------------------------------------- | -------------------------- |
| error     | [error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error) | The error that encountered |

```js
client.on('error', (error) => {
    console.log(`error: ${error}`);
});
```

### ***guildBanAdd***

Emitted whenever a member is banned from a guild.

| Parameter | Type                                                                 | Description           |
| --------- | -------------------------------------------------------------------- | --------------------- |
| ban       | [guildBan](https://discord.js.org/#/docs/main/stable/class/GuildBan) | The ban that occurred |

```js
client.on('guildBanAdd', (ban) => {
    console.log(`guildBanAdd: ${ban}`);
});
```


### ***guildBanRemove***

Emitted whenever a member is unbanned from a guild.

| Parameter | Type                                                                 | Description              |
| --------- | -------------------------------------------------------------------- | ------------------------ |
| ban       | [guildBan](https://discord.js.org/#/docs/main/stable/class/GuildBan) | The ban that was removed |

```js
client.on('guildBanRemove', (ban) => {
    console.log(`guildBanRemove: ${ban}`);
});
```

### ***guildCreate***

Emitted whenever the client joins a guild.

| Parameter | Type                                                           | Description       |
| --------- | -------------------------------------------------------------- | ----------------- |
| guild     | [Guild](https://discord.js.org/#/docs/main/stable/class/Guild) | The created guild |

```js
client.on('guildCreate', (guild) => {
    console.log(`guildCreate: ${guild}`);
});
```

### ***guildDelete***

Emitted whenever a guild kicks the client or the guild is deleted/left.

| Parameter | Type                                                           | Description                |
| --------- | -------------------------------------------------------------- | -------------------------- |
| guild     | [Guild](https://discord.js.org/#/docs/main/stable/class/Guild) | The guild that was deleted |

```js
client.on('guildDelete', (guild) => {
    console.log(`guildDelete: ${guild}`);
});
```

### ***guildIntegrationsUpdate***

Emitted whenever a guild integration is updated.

| Parameter | Type                                                           | Description                               |
| --------- | -------------------------------------------------------------- | ----------------------------------------- |
| guild     | [Guild](https://discord.js.org/#/docs/main/stable/class/Guild) | The guild whose integrations were updated |

```js
client.on('guildIntegrationsUpdate', (guild) => {
    console.log(`guildIntegrationsUpdate: ${guild}`);
});
```

### ***guildMemberAdd***

Emitted whenever a user joins a guild.

| Parameter | Type                                                                       | Description                        |
| --------- | -------------------------------------------------------------------------- | ---------------------------------- |
| member    | [GuildMember](https://discord.js.org/#/docs/main/stable/class/GuildMember) | The member that has joined a guild |

```js
client.on('guildMemberAdd', (member) => {
    console.log(`guildMemberAdd: ${member}`);
});
```

### ***guildMemberAvailable***

Emitted whenever a member becomes available in a large guild.

| Parameter | Type                                                                       | Description                      |
| --------- | -------------------------------------------------------------------------- | -------------------------------- |
| member    | [GuildMember](https://discord.js.org/#/docs/main/stable/class/GuildMember) | The member that became available |

```js
client.on('guildMemberAvailable', (member) => {
    console.log(`guildMemberAvailable: ${member}`);
});
```

### ***guildMemberRemove***

Emitted whenever a member leaves a guild, or is kicked.

| Parameter | Type                                                                       | Description                                         |
| --------- | -------------------------------------------------------------------------- | --------------------------------------------------- |
| member    | [GuildMember](https://discord.js.org/#/docs/main/stable/class/GuildMember) | The member that has left/been kicked from the guild |

```js
client.on('guildMemberRemove', (member) => {
    console.log(`guildMemberRemove: ${member}`);
});
```

### ***guildMembersChunk***

Emitted whenever a chunk of guild members is received (all members come from the same guild).

| Parameter | Type                                                                                                                                                                                                                               | Description                           |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| members   | [Collection](https://discord.js.org/#/docs/collection/main/class/Collection)<[Snowflake](https://discord.js.org/#/docs/main/stable/typedef/Snowflake), [GuildMember](https://discord.js.org/#/docs/main/stable/class/GuildMember)> | The members in the chunk              |
| guild     | [Guild](https://discord.js.org/#/docs/main/stable/class/Guild)                                                                                                                                                                     | The guild related to the member chunk |
| chunk     | [GuildMembersChunk](https://discord.js.org/#/docs/main/stable/typedef/GuildMembersChunk)                                                                                                                                           | Properties of the received chunk      |

```js
client.on('guildMembersChunk', (members, guild, chunk) => {
    console.log(`guildMemberRemove: ${members} | ${guild} | ${chunk}`);
});
```

### ***guildMemberUpdate***

Emitted whenever a guild member changes - i.e. new role, removed role, nickname.

| Parameter | Type                                                                       | Description                  |
| --------- | -------------------------------------------------------------------------- | ---------------------------- |
| oldMember | [GuildMember](https://discord.js.org/#/docs/main/stable/class/GuildMember) | The member before the update |
| newMember | [GuildMember](https://discord.js.org/#/docs/main/stable/class/GuildMember) | The member after the update  |

```js
client.on('guildMemberUpdate', (oldMember) => {
    console.log(`guildMemberUpdate: ${oldMember} | ${newMember}`);
});
```

### ***guildScheduledEventCreate***

Emitted whenever a guild scheduled event is created.

| Parameter           | Type                                                                                       | Description                       |
| ------------------- | ------------------------------------------------------------------------------------------ | --------------------------------- |
| guildScheduledEvent | [GuildScheduledEvent](https://discord.js.org/#/docs/main/stable/class/GuildScheduledEvent) | The created guild scheduled event |

```js
client.on('guildScheduledEventCreate', (guild) => {
    console.log(`guildScheduledEventCreate: ${guildScheduledEvent}`);
});
```

### ***guildScheduledEventDelete***

Emitted whenever a guild scheduled event is created.

| Parameter           | Type                                                                                       | Description                       |
| ------------------- | ------------------------------------------------------------------------------------------ | --------------------------------- |
| guildScheduledEvent | [GuildScheduledEvent](https://discord.js.org/#/docs/main/stable/class/GuildScheduledEvent) | The deleted guild scheduled event |

```js
client.on('guildScheduledEventCreate', (guild) => {
    console.log(`guildScheduledEventCreate: ${guildScheduledEvent}`);
});
```

### ***guildScheduledEventUpdate***

Emitted whenever a guild scheduled event gets updated.

| Parameter              | Type                                                                                       | Description                                        |
| ---------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------- |
| oldGuildScheduledEvent | [GuildScheduledEvent](https://discord.js.org/#/docs/main/stable/class/GuildScheduledEvent) | The guild scheduled event object before the update |
| newGuildScheduledEvent | [GuildScheduledEvent](https://discord.js.org/#/docs/main/stable/class/GuildScheduledEvent) | The guild scheduled event object after the update  |

```js
client.on('guildScheduledEventUpdate', (guild) => {
    console.log(`guildScheduledEventUpdate: ${oldGuildScheduledEvent} | ${newGuildScheduledEvent}`);
});
```

### ***guildScheduledEventUserAdd***

Emitted whenever a user subscribes to a guild scheduled event

| Parameter           | Type                                                                                       | Description               |
| ------------------- | ------------------------------------------------------------------------------------------ | ------------------------- |
| guildScheduledEvent | [GuildScheduledEvent](https://discord.js.org/#/docs/main/stable/class/GuildScheduledEvent) | The guild scheduled event |
| user                | [User](https://discord.js.org/#/docs/main/stable/class/User)                               | The user who subscribed   |

```js
client.on('guildScheduledEventUserAdd', (guild) => {
    console.log(`guildScheduledEventUserAdd: ${guildScheduledEvent} | ${user}`);
});
```

### ***guildScheduledEventUserRemove***

Emitted whenever a user unsubscribes from a guild scheduled event

| Parameter           | Type                                                                                       | Description               |
| ------------------- | ------------------------------------------------------------------------------------------ | ------------------------- |
| guildScheduledEvent | [GuildScheduledEvent](https://discord.js.org/#/docs/main/stable/class/GuildScheduledEvent) | The guild scheduled event |
| user                | [User](https://discord.js.org/#/docs/main/stable/class/User)                               | The user who unsubscribed |

```js
client.on('guildScheduledEventUserRemove', (guild) => {
    console.log(`guildScheduledEventUserRemove: ${guildScheduledEvent} | ${user}`);
});
```

### ***guildUnavailable***

Emitted whenever a guild becomes unavailable, likely due to a server outage.

| Parameter | Type                                                           | Description                           |
| --------- | -------------------------------------------------------------- | ------------------------------------- |
| guild     | [Guild](https://discord.js.org/#/docs/main/stable/class/Guild) | The guild that has become unavailable |

```js
client.on('guildUnavailable', (guild) => {
    console.log(`guildUnavailable: ${guild}`);
});
```

### ***guildUpdate***

Emitted whenever a guild is updated - e.g. name change.

| Parameter | Type                                                           | Description                 |
| --------- | -------------------------------------------------------------- | --------------------------- |
| oldGuild  | [Guild](https://discord.js.org/#/docs/main/stable/class/Guild) | The guild before the update |
| newGuild  | [Guild](https://discord.js.org/#/docs/main/stable/class/Guild) | The guild after the update  |

```js
client.on('guildUpdate', (oldGuild, newGuild) => {
    console.log(`guildUpdate: ${oldGuild} | ${newGuild}`);
});
```

### ***interaction***
> ⚠️ | This event is deprecated, use ***interactionCreate*** instead.

Emitted when an interaction is created.

| Parameter   | Type                                                                       | Description                       |
| ----------- | -------------------------------------------------------------------------- | --------------------------------- |
| interaction | [Interaction](https://discord.js.org/#/docs/main/stable/class/Interaction) | The interaction which was created |

```js
client.on('interaction', (interaction) => {
    console.log(`interaction: ${interaction}`);
});
```

### ***interactionCreate***

Emitted when an interaction is created.

| Parameter   | Type                                                                       | Description                       |
| ----------- | -------------------------------------------------------------------------- | --------------------------------- |
| interaction | [Interaction](https://discord.js.org/#/docs/main/stable/class/Interaction) | The interaction which was created |

```js
client.on('interactionCreate', (interaction) => {
    console.log(`interactionCreate: ${interaction}`);
});
```

### ***invalidated***

Emitted when the client's session becomes invalidated. You are expected to handle closing the process gracefully and preventing a boot loop if you are listening to this event.

```js
client.on('invalidated', () => {
    console.log(`invalidated`);
});
```

### ***invalidRequestWarning***

Emitted periodically when the process sends invalid requests to let users avoid the 10k invalid requests in 10 minutes threshold that causes a ban.

| Parameter                 | Type                                                                                                     | Description                                |
| ------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| invalidRequestWarningData | [invalidRequestWarningData](https://discord.js.org/#/docs/main/stable/typedef/InvalidRequestWarningData) | Object containing the invalid request info |

```js
client.on('invalidRequestWarning', (invalidRequestWarningData) => {
    console.log(`invalidRequestWarning: ${invalidRequestWarningData}`);
});
```

### ***inviteCreate***

> ℹ️ | This event only triggers if the client has `MANAGE_GUILD` permissions for the guild, or `MANAGE_CHANNELS` permissions for the channel.

Emitted when an invite is created.

| Parameter | Type                                                             | Description                 |
| --------- | ---------------------------------------------------------------- | --------------------------- |
| invite    | [Invite](https://discord.js.org/#/docs/main/stable/class/Invite) | The invite that was created |

```js
client.on('inviteCreate', (invite) => {
    console.log(`inviteCreate: ${invite}`);
});
```

### ***inviteDelete***

> ℹ️ | This event only triggers if the client has `MANAGE_GUILD` permissions for the guild, or `MANAGE_CHANNELS` permissions for the channel.

Emitted when an invite is deleted.

| Parameter | Type                                                             | Description                 |
| --------- | ---------------------------------------------------------------- | --------------------------- |
| invite    | [Invite](https://discord.js.org/#/docs/main/stable/class/Invite) | The invite that was deleted |

```js
client.on('inviteDelete', (invite) => {
    console.log(`inviteDelete: ${invite}`);
});
```

### ***message***

> ⚠️ | This event is deprecated, use ***messageCreate*** instead.

Emitted when a message is created.

| Parameter | Type                                                               | Description         |
| --------- | ------------------------------------------------------------------ | ------------------- |
| message   | [Message](https://discord.js.org/#/docs/main/stable/class/Message) | The created message |

```js
client.on('message', (message) => {
    console.log(`message: ${message}`);
});
```

### ***messageCreate***

Emitted when a message is created.

| Parameter | Type                                                               | Description         |
| --------- | ------------------------------------------------------------------ | ------------------- |
| message   | [Message](https://discord.js.org/#/docs/main/stable/class/Message) | The created message |

```js
client.on('messageCreate', (message) => {
    console.log(`messageCreate: ${message}`);
});
```

### ***messageDelete***

Emitted whenever a message is deleted.

| Parameter | Type                                                               | Description         |
| --------- | ------------------------------------------------------------------ | ------------------- |
| message   | [Message](https://discord.js.org/#/docs/main/stable/class/Message) | The deleted message |

```js
client.on('messageDelete', (message) => {
    console.log(`messageDelete: ${message}`);
});
```

### ***messageDeleteBulk***

Emitted whenever messages are deleted in bulk.

| Parameter | Type                                                                                                                                                                                                                       | Description                              |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| messages  | [Collection](https://discord.js.org/#/docs/collection/main/class/Collection)<[Snowflake](https://discord.js.org/#/docs/main/stable/typedef/Snowflake), [Message](https://discord.js.org/#/docs/main/stable/class/Message)> | The deleted messages, mapped by their id |

```js
client.on('messageDeleteBulk', (messages) => {
    console.log(`messageDeleteBulk: ${messages}`);
});
```

### ***messageReactionAdd***

Emitted whenever a reaction is added to a cached message.

| Parameter       | Type                                                                               | Description                                       |
| --------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------- |
| messageReaction | [MessageReaction](https://discord.js.org/#/docs/main/stable/class/MessageReaction) | The reaction object                               |
| user            | [User](https://discord.js.org/#/docs/main/stable/class/User)                       | The user that applied the guild or reaction emoji |

```js
client.on('messageReactionAdd', (reaction, user) => {
    console.log(`messageReactionAdd: ${reaction} | ${user}`);
});
```

### ***messageReactionRemove***

Emitted whenever a reaction is removed from a cached message.

| Parameter       | Type                                                                               | Description                                        |
| --------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------- |
| messageReaction | [MessageReaction](https://discord.js.org/#/docs/main/stable/class/MessageReaction) | The reaction object                                |
| user            | [User](https://discord.js.org/#/docs/main/stable/class/User)                       | The user whose emoji or reaction emoji was removed |

```js
client.on('messageReactionRemove', (reaction, user) => {
    console.log(`messageReactionRemove: ${reaction} | ${user}`);
});
```

### ***messageReactionRemoveAll***

Emitted whenever all reactions are removed from a cached message.

| Parameter | Type                                                                                                                                                                                                                                                                                                                                            | Description                                    |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| message   | [Message](https://discord.js.org/#/docs/main/stable/class/Message)                                                                                                                                                                                                                                                                              | The message the reactions were removed from    |
| reactions | [Collection](https://discord.js.org/#/docs/collection/main/class/Collection)<[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [Snowflake](https://discord.js.org/#/docs/main/stable/typedef/Snowflake), [MessageReaction](https://discord.js.org/#/docs/main/stable/class/MessageReaction)> | The cached message reactions that were removed |

```js
client.on('messageReactionRemoveAll', (message, reactions) => {
    console.log(`messageReactionRemoveAll: ${message} | ${reactions}`);
});
```

### ***messageReactionRemoveEmoji***

Emitted when a bot removes an emoji reaction from a cached message.

| Parameter | Type                                                                               | Description                   |
| --------- | ---------------------------------------------------------------------------------- | ----------------------------- |
| reaction  | [MessageReaction](https://discord.js.org/#/docs/main/stable/class/MessageReaction) | The reaction that was removed |

```js
client.on('messageReactionRemoveEmoji', (reaction) => {
    console.log(`messageReactionRemoveEmoji: ${reaction}`);
});
```

### ***messageUpdate***

Emitted whenever a message is updated - e.g. embed or content change.

| Parameter  | Type                                                               | Description                   |
| ---------- | ------------------------------------------------------------------ | ----------------------------- |
| oldMessage | [Message](https://discord.js.org/#/docs/main/stable/class/Message) | The message before the update |
| newMessage | [Message](https://discord.js.org/#/docs/main/stable/class/Message) | The message after the update  |

```js
client.on('messageUpdate', (oldMessage, newMessage) => {
    console.log(`messageUpdate: ${oldMessage} | ${newMessage}`);
});
```

### ***presenceUpdate***

Emitted whenever a guild member's presence (e.g. status, activity) is changed.

| Parameter   | Type                                                                  | Description                                   |
| ----------- | --------------------------------------------------------------------- | --------------------------------------------- |
| oldPresence | ?[Presence](https://discord.js.org/#/docs/main/stable/class/Presence) | The presence before the update, if one at all |
| newPresence | [Presence](https://discord.js.org/#/docs/main/stable/class/Presence)  | The presence after the update                 |

```js
client.on('presenceUpdate', (oldPresence, newPresence) => {
    console.log(`presenceUpdate: ${oldPresence} | ${newPresence}`);
});
```

### ***rateLimit***

Emitted when the client hits a rate limit while making a request.

| Parameter     | Type                                                                             | Description                           |
| ------------- | -------------------------------------------------------------------------------- | ------------------------------------- |
| rateLimitData | [RateLimitData](https://discord.js.org/#/docs/main/stable/typedef/RateLimitData) | Object containing the rate limit info |


```js
client.on('rateLimit', (rateLimitData) => {
    console.log(`rateLimit: ${rateLimitData}`);
});
```

### ***ready***

Emitted when the client becomes ready to start working.

| Parameter | Type                                                             | Description |
| --------- | ---------------------------------------------------------------- | ----------- |
| client    | [Client](https://discord.js.org/#/docs/main/stable/class/Client) | The client  |


```js
client.on('ready', (client) => {
    console.log(`ready: ${client}`);
});
```

### ***roleCreate***

Emitted whenever a role is created.

| Parameter | Type                                                         | Description               |
| --------- | ------------------------------------------------------------ | ------------------------- |
| role      | [Role](https://discord.js.org/#/docs/main/stable/class/Role) | The role that was created |


```js
client.on('roleCreate', (role) => {
    console.log(`roleCreate: ${role}`);
});
```

### ***roleDelete***

Emitted whenever a role is deleted.

| Parameter | Type                                                         | Description               |
| --------- | ------------------------------------------------------------ | ------------------------- |
| role      | [Role](https://discord.js.org/#/docs/main/stable/class/Role) | The role that was deleted |


```js
client.on('roleDelete', (role) => {
    console.log(`roleDelete: ${role}`);
});
```

### ***roleUpdate***

Emitted whenever a role is updated.

| Parameter | Type                                                         | Description                |
| --------- | ------------------------------------------------------------ | -------------------------- |
| oldRole   | [Role](https://discord.js.org/#/docs/main/stable/class/Role) | The role before the update |
| newRole   | [Role](https://discord.js.org/#/docs/main/stable/class/Role) | The role after the update  |


```js
client.on('roleUpdate', (oldRole, newRole) => {
    console.log(`roleUpdate: ${oldRole} | ${newRole}`);
});
```

### ***shardDisconnect***

Emitted when a shard's WebSocket disconnects and will no longer reconnect.

| Parameter | Type                                                                                              | Description                    |
| --------- | ------------------------------------------------------------------------------------------------- | ------------------------------ |
| event     | [CloseEvent](https://developer.mozilla.org/en-US/docs/Web/API/CloseEvent)                         | The WebSocket cloes event      |
| id        | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | The shard id that disconnected |


```js
client.on('shardDisconnect', (event, id) => {
    console.log(`shardDisconnect: ${event} | ${id}`);
});
```

### ***shardError***

Emitted whenever a shard's WebSocket encounters a connection error.

| Parameter | Type                                                                                              | Description                           |
| --------- | ------------------------------------------------------------------------------------------------- | ------------------------------------- |
| error     | [Error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)   | The encountered error                 |
| shardId   | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | The shard that encountered this error |


```js
client.on('shardError', (error, shardId) => {
    console.log(`shardError: ${error} | ${shardId}`);
});
```

### ***shardReady***

Emitted when a shard turns ready.

| Parameter         | Type                                                                                                                                                                   | Description                          |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| id                | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)                                                                      | The shard id that turned ready       |
| unavailableGuilds | ?[Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)<[Snowflake](https://discord.js.org/#/docs/main/stable/typedef/Snowflake)> | Set of unavailable guild ids, if any |


```js
client.on('shardReady', (id, unavailableGuilds) => {
    console.log(`shardError: ${id} | ${unavailableGuilds}`);
});
```

### ***shardReconnecting***

Emitted when a shard is attempting to reconnect or re-identify.

| Parameter | Type                                                                                              | Description                                  |
| --------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| id        | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | The shard id that is attempting to reconnect |


```js
client.on('shardReconnecting', (id) => {
    console.log(`shardReconnecting: ${id}`);
});
```

### ***shardResume***

Emitted when a shard resumes successfully.

| Parameter      | Type                                                                                              | Description                   |
| -------------- | ------------------------------------------------------------------------------------------------- | ----------------------------- |
| id             | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | The shard id that resumed     |
| replayedEvents | [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | The amount of replayed events |

```js
client.on('shardResume', (id, replayedEvents) => {
    console.log(`shardReconnecting: ${id} | ${replayedEvents}`);
});
```

### ***stageInstanceCreate***

Emitted whenever a stage instance is created.

| Parameter     | Type                                                                           | Description                |
| ------------- | ------------------------------------------------------------------------------ | -------------------------- |
| stageInstance | [StageInstance](https://discord.js.org/#/docs/main/stable/class/StageInstance) | The created stage instance |

```js
client.on('stageInstanceCreate', (stageInstance) => {
    console.log(`stageInstanceCreate: ${stageInstance}`);
});
```

### ***stageInstanceDelete***

Emitted whenever a stage instance is deleted.

| Parameter     | Type                                                                           | Description                |
| ------------- | ------------------------------------------------------------------------------ | -------------------------- |
| stageInstance | [StageInstance](https://discord.js.org/#/docs/main/stable/class/StageInstance) | The deleted stage instance |

```js
client.on('stageInstanceDelete', (stageInstance) => {
    console.log(`stageInstanceDelete: ${stageInstance}`);
});
```

### ***stageInstanceUpdate***

Emitted whenever a stage instance gets updated - e.g. change in topic or privacy level.

| Parameter        | Type                                                                            | Description                          |
| ---------------- | ------------------------------------------------------------------------------- | ------------------------------------ |
| oldStageInstance | ?[StageInstance](https://discord.js.org/#/docs/main/stable/class/StageInstance) | The stage instance before the update |
| newStageInstance | [StageInstance](https://discord.js.org/#/docs/main/stable/class/StageInstance)  | The stage instance after the update  |

```js
client.on('stageInstanceUpdate', (oldStageInstance, newStageInstance) => {
    console.log(`stageInstanceUpdate: ${oldStageInstance} | ${newStageInstance}`);
});
```

### ***stickerCreate***

Emitted whenever a custom sticker is created in a guild.

| Parameter | Type                                                               | Description                  |
| --------- | ------------------------------------------------------------------ | ---------------------------- |
| sticker   | [Sticker](https://discord.js.org/#/docs/main/stable/class/Sticker) | The sticker that was created |

```js
client.on('stickerCreate', (sticker) => {
    console.log(`stickerCreate: ${sticker}`);
});
```


### ***stickerDelete***

Emitted whenever a custom sticker is deleted in a guild.

| Parameter | Type                                                               | Description                  |
| --------- | ------------------------------------------------------------------ | ---------------------------- |
| sticker   | [Sticker](https://discord.js.org/#/docs/main/stable/class/Sticker) | The sticker that was deleted |

```js
client.on('stickerDelete', (sticker) => {
    console.log(`stickerDelete: ${sticker}`);
});
```

### ***stickerUpdate***

Emitted whenever a custom sticker is deleted in a guild.

| Parameter  | Type                                                               | Description     |
| ---------- | ------------------------------------------------------------------ | --------------- |
| oldSticker | [Sticker](https://discord.js.org/#/docs/main/stable/class/Sticker) | The old sticker |
| newSticker | [Sticker](https://discord.js.org/#/docs/main/stable/class/Sticker) | The new sticker |

```js
client.on('stickerUpdate', (oldSticker, newSticker) => {
    console.log(`stickerUpdate: ${oldSticker} | ${newSticker}`);
});
```

### ***threadCreate***

Emitted whenever a thread is created or when the client user is added to a thread.

| Parameter | Type                                                                           | Description                 |
| --------- | ------------------------------------------------------------------------------ | --------------------------- |
| thread    | [ThreadChannel](https://discord.js.org/#/docs/main/stable/class/ThreadChannel) | The thread that was created |

```js
client.on('threadCreate', (thread) => {
    console.log(`threadCreate: ${thread}`);
});
```

### ***threadDelete***

Emitted whenever a thread is created or when the client user is added to a thread.

| Parameter | Type                                                                           | Description                 |
| --------- | ------------------------------------------------------------------------------ | --------------------------- |
| thread    | [ThreadChannel](https://discord.js.org/#/docs/main/stable/class/ThreadChannel) | The thread that was deleted |

```js
client.on('threadDelete', (thread) => {
    console.log(`threadDelete: ${thread}`);
});
```
### ***threadListSync***

Emitted whenever the client user gains access to a text or news channel that contains threads

| Parameter | Type                                                                                                                                                                                                                                   | Description                  |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| threads   | [Collection](https://discord.js.org/#/docs/collection/main/class/Collection)<[Snowflake](https://discord.js.org/#/docs/main/stable/typedef/Snowflake), [ThreadChannel](https://discord.js.org/#/docs/main/stable/class/ThreadChannel)> | The threads that were synced |

```js
client.on('threadListSync', (threads) => {
    console.log(`threadListSync: ${threads}`);
});
```

### ***threadMembersUpdate***

Emitted whenever members are added or removed from a thread. 

| Parameter  | Type                                                                                                                                                                                                                                 | Description                   |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------- |
| oldMembers | [Collection](https://discord.js.org/#/docs/collection/main/class/Collection)<[Snowflake](https://discord.js.org/#/docs/main/stable/typedef/Snowflake), [ThreadMember](https://discord.js.org/#/docs/main/stable/class/ThreadMember)> | The members before the update |
| newMembers | [Collection](https://discord.js.org/#/docs/collection/main/class/Collection)<[Snowflake](https://discord.js.org/#/docs/main/stable/typedef/Snowflake), [ThreadMember](https://discord.js.org/#/docs/main/stable/class/ThreadMember)> | The members after the update  |

```js
client.on('threadMembersUpdate', (oldMembers, newMembers) => {
    console.log(`threadMembersUpdate: ${oldMembers} | ${newMembers}`);
});
```

### ***threadMemberUpdate***

Emitted whenever the client user's thread member is updated.

| Parameter | Type                                                                         | Description                  |
| --------- | ---------------------------------------------------------------------------- | ---------------------------- |
| oldMember | [ThreadMember](https://discord.js.org/#/docs/main/stable/class/ThreadMember) | The member before the update |
| newMember | [ThreadMember](https://discord.js.org/#/docs/main/stable/class/ThreadMember) | The member after the update  |

```js
client.on('threadMemberUpdate', (oldMember, newMember) => {
    console.log(`threadMemberUpdate: ${oldMember} | ${newMember}`);
});
```

### ***threadUpdate***

Emitted whenever a thread is updated - e.g. name change, archive state change, locked state change.

| Parameter | Type                                                                           | Description                  |
| --------- | ------------------------------------------------------------------------------ | ---------------------------- |
| oldThread | [ThreadChannel](https://discord.js.org/#/docs/main/stable/class/ThreadChannel) | The thread before the update |
| newThread | [ThreadChannel](https://discord.js.org/#/docs/main/stable/class/ThreadChannel) | The thread after the update  |

```js
client.on('threadUpdate', (oldThread, newThread) => {
    console.log(`threadUpdate: ${oldThread} | ${newThread}`);
});
```

### ***typingStart***

Emitted whenever a user starts typing in a channel.

| Parameter | Type                                                             | Description      |
| --------- | ---------------------------------------------------------------- | ---------------- |
| typing    | [Typing](https://discord.js.org/#/docs/main/stable/class/Typing) | The typing state |

```js
client.on('typingStart', (typing) => {
    console.log(`typingStart: ${typing}`);
});
```

### ***userUpdate***
> ℹ️ | Triggered by the Discord gateway events `USER_UPDATE`, `GUILD_MEMBER_UPDATE`, and `PRESENCE_UPDATE`.

Emitted whenever a user's details (e.g. username) are changed.

| Parameter | Type                                                         | Description                |
| --------- | ------------------------------------------------------------ | -------------------------- |
| oldUser   | [User](https://discord.js.org/#/docs/main/stable/class/User) | The user before the update |
| newUser   | [User](https://discord.js.org/#/docs/main/stable/class/User) | The user after the update  |


```js
client.on('userUpdate', (oldUser, newUser) => {
    console.log(`userUpdate: ${oldUser} | ${newUser}`);
});
```

### ***voiceStateUpdate***

Emitted whenever a member changes voice state - e.g. joins/leaves a channel, mutes/unmutes.

| Parameter | Type                                                                     | Description                       |
| --------- | ------------------------------------------------------------------------ | --------------------------------- |
| oldState  | [VoiceState](https://discord.js.org/#/docs/main/stable/class/VoiceState) | The voice state before the update |
| newState  | [VoiceState](https://discord.js.org/#/docs/main/stable/class/VoiceState) | The voice state after the update  |


```js
client.on('voiceStateUpdate', (oldUser, newUser) => {
    console.log(`voiceStateUpdate: ${oldState} | ${newState}`);
});
```

### ***warn***

Emitted for general warnings.

| Parameter | Type                                                                                              | Description |
| --------- | ------------------------------------------------------------------------------------------------- | ----------- |
| info      | [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | The warning |


```js
client.on('warn', (info) => {
    console.log(`warn: ${info}`);
});
```

### ***webhookUpdate***

Emitted whenever a channel has its webhooks changed.

| Parameter | Type                                                                                                                                                     | Description                           |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------- |
| channel   | [TextChannel](https://discord.js.org/#/docs/main/stable/class/TextChannel) or [NewsChannel](https://discord.js.org/#/docs/main/stable/class/NewsChannel) or [VoiceChannel](https://discord.js.org/#/docs/main/stable/class/VoiceChannel) | The channel that had a webhook update |


```js
client.on('webhookUpdate', (channel) => {
    console.log(`webhookUpdate: ${channel}`);
});
```
