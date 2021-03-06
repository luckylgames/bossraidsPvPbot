# Meowth
A Discord helper bot for Pokemon Go communities.


Meowth is a Discord bot written in Python 3.5 using version 0.16.8 of the discord.py library. Directions for installing
and running on your server:

1. Install Python 3.5 for whatever OS you have on your home computer. https://www.python.org/downloads/release/python-350/
2. Install discord.py. To do this, run this command in your command prompt: python3 -m pip install -U discord.py
(On Windows: py -m pip install -U discord.py should work)

3. Download the files in this repository. The source code is in meowth.py, the rest of the files are images for the custom emoji
that Meowth uses.

4. Go here https://discordapp.com/developers/applications/me#top and create a new app. Name it Meowth if you like and upload the 
Meowth avatar included in the repository. Create a bot user for your app.

5. Copy this link. https://discordapp.com/oauth2/authorize?client_id=<CLIENT_ID>&scope=bot Paste it into your browser.
Then go to your Discord application page again and copy the client id, inserting it into the above link where it says <CLIENT_ID>.
Press enter and select the server you want to add Meowth too.

6. Give Meowth admin privileges.

7. If you haven't already, create a role for each team. The role ids need to be copied and pasted to lines 83-85 of meowth.py.

7. Upload the other images as custom emoji for your server. There are 18 type icons, an omw emoji (car), an unomw emoji (car with
a circle and a line through it), and here and unhere emoji (Go Plus), and an emoji for each of the three teams.

8. Open meowth.py in IDLE. You'll need to make a few more easy edits. First, you'll need to replace the custom emoji with the 
strings that bots use to use the custom emoji. To find that string, in a Discord channel, type \:mystic: to get the string for 
the Team Mystic emoji. Then replace any instance of the :mystic: emoji in the code with that string. You'll have to do this for 
each of the 25 custom emoji. The following lines of the code have custom emoji that have to be replaced. 13-39, 879, 1022, 1023, 
1024, 1026, 1027, 1028, 1033, 1038.

9. In lines 940 and 964, replace "yourtown+yourstate" with your community's location. This makes the Google Maps thing work a lot better.

10. Go back to your app page in Discord and click to reveal the bot token, then copy it and paste it into line 1122. 
Save meowth.py.

11. Run meowth.py from the command prompt or terminal window. If successful, it should print "Meowth! That's right!" to the 
window and the bot should show up as online in Discord.




Directions for using Meowth (avoid punctuation of any kind inside commands, the <> are there for decoration):

1. !team <teamname> - adds you to a team role on the server. These roles must be created beforehand.

2. !want <pokemonname> - adds you to an invisible role for a Pokemon. Meowth will create a role if none exists.

3. !wild <pokemonname> <location> - Meowth will send a message @mentioning <pokemonname> and including a Google Maps link
to <location>. If <location> is blank, Meowth will ask for more details.

4. !raid <pokemonname> <location> - Does the same thing as !wild, but also creates a new channel by the name of
#<pokemonname>-<location>. The message also includes the custom emoji for the types that do super effective damage against the 
Pokemon. The created raid channel will automatically delete in two hours.

5. :omw:/:here: - in a raid channel, the custom emoji for omw and here tell Meowth that you are on your way to or at a raid.
If you have multiple trainers with you, type another emoji for each additional trainer. Typing :here: also removes you from the
on the way list.

6. :unomw:/:unhere: - in a raid channel, these custom emoji tell Meowth to remove you from the on the way or waiting lists.

7. !otw/!waiting - in a raid channel, these commands tell Meowth to list and mention the trainers who said they were on the way
or at a raid. It also includes the total number.

8. !starting - in a raid channel, this command tells Meowth to delete the !waiting list for that raid. Meowth will mention the
users and ask them to respond with :here: if they are still waiting.

9. !timerset H:MM - in a raid channel, this tells Meowth how long is remaining on the raid. Meowth will send a message notifying
the time at which the raid will end. Also overwrites any previously used !timerset command for that raid.

10. !timer - in a raid channel, tells Meowth to resend the message from the last !timerset command. Prevents unnecessary
scrolling.

General notes on Meowth:
Meowth relies completely on user reports of raids, wild spawns, on the way to a raid, at a raid, and starting a raid. Meowth
was designed as an alternative to Discord bots that use scanners and other illegitimate sources of information about Pokemon Go.
As a result, Meowth works only as well as the users who use it. As there are 10+ ways of interacting with Meowth, there
can be a bit of a rough learning period, but it quickly becomes worth it.

Known issues:
Compatibility with Python 3.6+ or discord.py 1.0 is currently unknown.
Occassional failure to remove users from on the way or waiting lists, cause unknown.
Complete inability to deal with misspelled Pokemon names.

