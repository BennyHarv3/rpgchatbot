# rpgchatbot
Chatbot to generate RPG scenarios and (eventually) play short sessions

## How to Use
Go to the RPG ChatBot Facebook page to send the page a message. If you are unable to do so, it's because the page isn't published. Check with me for access.

Send the chatbot any message you want, and right now, all it does is echo it back at you. More to come!

## What's Behind the ChatBot
RPG ChatBot uses [wit.ai](wit.ai) as the AI engine to process user messages.

## How to Contribute
Check with me. You can create as many pull requests as you want, but deployment hasn't been automated yet.

### Why 2 index.js Files?
I originally hosted this on [Heroku](heroku.com) and used the express-index.js file to run the chatbot with [Express](expressjs.com). Now, the chatbot is running on [AWS Lambda services](https://aws.amazon.com/lambda/), but I haven't removed the express-index.js file just yet because I hate deleteing files I may one day (but probably never) need. Consider it dead.

### What to Contribute
There are clearly lots of things to do! If you want to help out, here are the high-level next steps for the project.
1. Let's make a tavern!
   1. The aws-index.js file needs to have a function that returns a tavern.
	  1. To start, returning the same tavern description would be fine.
	  2. Eventually, we'd like to prompt the user for the type of tavern they wanted to have.
	  3. We could probably also figure out party size at some point, but that's way down the line.
   2. The wit.ai engine needs trained on the word tavern and what to return.
	  1. Ideally, the wit.ai engine would return the tavern description directly to us, but I haven't figured out how to get that working.
	  2. The AI engine would also need to do all of the stuff from the first point.
   3. The aws-index.js file needs to call the tavern function correctly.
2. Start an adventure! Repeat the above stuff, just for different adventure modules.
   1. Each adventure should be encapsulated in its own module.
   2. Any rules an adventure would need would likely need support in the main files as well.
3. Make a party or save a character!
4. Maybe put some hard rules in? I would prefer if rules could be encapsulated in adventures, but if people wanted to start playing D&D with the chatbot and not just some text-based adventure, we'd probably need some support.

### Tavern Chat Flow
This is how I envision one of the ways to get a tavern. There are clearly many more, but we'll start with one. Since we're still super basic, it may not even be useful.
User > Hi!
Chatbot > Hello! Welcome to RPG Chatbot! I'm still under development, but let's set the scene for a game.
Chatbot > Right now, I can make the following locations: tavern
Chatbot > What would you like to do?
User > Start in a tavern
Chatbot > <tavern description>
