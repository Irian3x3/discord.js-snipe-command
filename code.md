## About `<client>.snipes`
Go to your main file (usually `index.js` or `bot.js` and the following code:
```js
<client>.snipes = new Discord.Collection();
```

- Note: Replace `<client>` with your client variable (usually `client` or `bot`).

## Snipe command code:
```js
       try {
            const embed = new Discord.MessageEmbed()
                .setAuthor(`${<client>.snipes.get(message.channel.id).author.tag}`, `${bot.snipes.get(message.channel.id).author.displayAvatarURL({ dynamic: true, format: 'png' })}`)
                .setDescription(`${<client>.snipes.get(message.channel.id).content}`)
                .setColor('RANDOM')
                .setTimestamp(`${<client>.snipes.get(message.channel.id).timestamp}`)
            message.channel.send(embed)
        } catch () {
            message.channel.send(`There's nothing to snipe!`);
        };
```
