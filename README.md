
11/07/19 
Since my last project I've been working to build a simple game engine for text adventures. 
I chose this in particular because it seemed like a good way to better understand things, as when you're making a game engine, you cannot reply on IDEs too much as you're basically making one. For instance, I want to make a window appear, no problem go to VB and create a new windows forms project, except if you're making a program that makes programs that are windows forms that doesn't work.

It's been months I've been working on this and I'm not even out of the gates. This is partly because as something I do in my free time, I'm only working on this about 6-9 hours a week, but it's mostly due to my lack of knowledge and experience, something I hope is going to get better at time. 

I have a rough idea of how I want it to work. Basically the user will be given a simple drag and drop GUI for branching story lines, text, images, sound and encounters. Behind the scenes everything is pretty much already laid out and the user is just using the GUI to fill in the blanks. "create these NPC's and set their stats to this", "have them say this is the user does that", "play this tune when the player does this" that sort of thing. 

I'm am planning on using the SlimDX API for the graphics, which is completely unnecessary. Had I decided to go with my other option,  Mono, I would be way further ahead by now due to it's simplicity, it could also make games compatible with Linux. Mono has all of the features that need since we're only rendering text, some 2D colours, some sound, JPEGs and maybe some very simple animations, having a full on graphics API like SlimDX is completely unnecessary.

However my thought process went something like this.
"Mono looks really simple, there are easy step-by-step guides on how to do everything I need and could enable people to make their games for Linux. Learning it could also have some real world practical use, perfect for a beginner like me"
"SlimDX, thats like, games. Games are made from SlimDX, its a video games thing"

I'm a moron.

For now all I have is a compiler. It takes text in one box and then makes an exe by interpreting that as C# code. I have a few examples of code that will work to make a window appear but I'm still wrapping my head around SlimDX. I'll upload my code for that later.
