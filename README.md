## Running

Execute the following in your shell or prompt:
```
node index.js
```

Use [PM2](https://www.npmjs.com/package/pm2) to keep the bot running 24/7, it will also restart the bot in case of a crash or on memory limits (2GB default):
```
pm2 start ecosystem.config.js
```

## Usage
By now you have a discord server.
Make sure your server has a text and voice channel.

1. Enter one of your voice channels.
2. In one of your text channels type: `!join`
3. Type `!help` for a list of commands.

Examples:

```
!play https://www.youtube.com/watch?v=vK1YiArMDfg
!play red hot chili peppers californication
!list
!skip
```

### Voice commands

When the bot is inside a voice channel it listens to all speech and tries to detect commands.

Try saying:
```
melody play 'counting starts'
melody skip
melody play random
melody list
melody clear list
```

A successful voice command looks like this:

`<long pause>   melody play 'trevor daniel falling'   <long pause>`

### Notes: 
- Each voice command starts with `melody`.
- Each user talks to a separate channel, the bot hears every user separately.
- Only when your user picture turns green in the voice channel will the bot receive your audio.
- A long pause interrupts the audio input.
- (WitAI only) The duration of a single audio input is limited to 6 seconds, longer audio is not transcribed.

Here are some examples which may not work (properly):
```
<talking> melody skip
melody skip <talking>
<talking> melody skip <talking>
...

melody play 'counting stars' <talking>

music <long silence>  play  <long silence> 'counting stars'
```


### Notes:
- A successful voice command should contain as little noise before and after the command.
- A successful voice command should should not contain too many/long periods of silence, otherwise the bot will only receive separate words instead of the whole sentence.
- `<long pause>` is usually between 1 and 2 seconds, long enough for discord to stop processing your audio input.
- If you have a very sensitive microphone or a lot of (background) noise, then voice commands may not work properly for you.
