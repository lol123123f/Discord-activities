# How to install

```py
pip install discord-activity
```

# set up
ac = activities.activity("Your bot token")

```py
import discord
bot = discord.Client()
ac = activities.activity(TOKEN)

@bot.event  
async def on_ready():  
    print(f"The bot {bot.user.name} is up")

if __name__ == "__main__":  
    bot.run(TOKEN)
```
## Features
- **get invite link to activity**
- **icon_url**
- **name**
- **created_at (Invite code)**
- **expires_at (Invite code)**


## Activity included 
- **Watch_Together**
- **Poker_Night**
- **Betrayal_io**
- **Fishington_io**
- **Chess_In_The_Park**
- **Sketchy_Artist**
- **Awkword**
- **Delete_Me_Calla**
- **Doodle_Crew**
- **Sketch_Heads**
- **Letter_League**
- **Word_Snacks**
- **SpellCast**
- **Checkers_In_The_Park**
- **Blazing_8s**
- **Putt_Party**
- **Land_io**
- **Bobble_League**
- **Ask_Away**
- **Know_What_I_Meme**


## Set activity channel
```py
import discord
bot = discord.Client()
ac = activities.activity(TOKEN)

@bot.event  
async def on_ready():  
    print(f"The bot {bot.user.name} is up")

@bot.event 
async def on_message(msg):
	args = msg.content.split()
	if args[0] == f"ac":
		ac_var = ac.new_link(msg.channel, activities.get_id_of().Watch_Together)

if __name__ == "__main__":  
    bot.run(TOKEN)
```


## Get name/link/icon url/created_at/expires_at example/channel
```py
import discord
bot = discord.Client()
ac = activities.activity(TOKEN)

@bot.event  
async def on_ready():  
    print(f"The bot {bot.user.name} is up")

@bot.event 
async def on_message(msg):
	args = msg.content.split()
	if args[0] == f"ac":
		ac_var = ac.new_link(msg.channel, activities.get_id_of().Watch_Together)
		ac_var.name  
		ac_var.channel  
		ac_var.created_at  
		ac_var.expires_at  
		ac_var.icon_url  
		ac_var.link

if __name__ == "__main__":  
    bot.run(TOKEN)
```


# Embed
```py
import discord
bot = discord.Client()
ac = activities.activity(TOKEN)

@bot.event  
async def on_ready():  
    print(f"The bot {bot.user.name} is up")

@bot.event 
async def on_message(msg):
	args = msg.content.split()
	if args[0] == f"ac":
		ac_var = ac.new_link(msg.channel, activities.get_id_of().Watch_Together)
		await msg.channl.send(ac_var.make_embed())

if __name__ == "__main__":  
    bot.run(TOKEN)
```

![Example](https://i.ibb.co/mG58X4F/Screenshot-2022-08-07-003626.png)



## The embed code
You can just change the values you want 
```py
embed_var = discord.Embed(title=self.name, description=f"[Press here]({self.link})")  
embed_var.add_field(name="created at:", value=self.created_at[:10])  
embed_var.add_field(name="end at:", value=self.expires_at[:10])  
embed_var.add_field(name="Channel:", value=self.channel.mention)  
embed_var.set_thumbnail(url=self.icon_url)  
return embed_var
```

## Get all Activity as dictionary
```py
activities.get_id_of.to_dict()
```
Will return a dictionary that work like this:
Name = id
activities.get_id_of.to_dict()["Watch_Together"] will return the Watch_Together id
