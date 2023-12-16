# liisabotti

_Liisabotti_ was a IRC chatbot developed in 2000. It was running on Finnish language IRC channels in the _IRCnet_ between years 2000 and 2004.

The bot joined IRC channels where it was invited and listened to conversations of channel participants. It was also able to have private chats with other IRC users.

Read more about IRC and IRC bots:
- https://en.wikipedia.org/wiki/Internet_Relay_Chat
- https://en.wikipedia.org/wiki/IRC_bot

**Purpose of this repository**

This project has been made public to preserve a piece of IRC history and also to showcase an early days implementation of something that nowadays (in 2023) could be called artificial intelligence (AI). 

In year 2000 many of the terms related to AI were not yet invented.

The source code of Liisabotti consists mostly of code related to the bots IRC protocol related functions. The more interesting parts described below were technically very simple and didn't take much lines of code.


**Chat Generative Pre-trained Transformer**

ChatGPT is currently massively popular, but in principle it is just a massively scaled and distributed version of what _Liisabotti_ was in 2000.

Liisabotti uses pre-processed data to figure out how to answer to it's users. In addition it uses a very simple word matching algorithm to understand context of the incoming messages. This context is used to add new sentences to the bots database. The original version of the bot used Finnish language in it's word detection algorithm, making it appear bit more smarter than expected when used by an user from Finland.

The bot runs as a single process and uses a single on-disk database, therefore every user who interacted with the bot between years 2000 and 2004 participated in training the bot.

In May 2000 the database had 334654 words or 15023 sentences, mostly in Finnish. In comparison, ChatGPT had 17 trillion words in year 2022. Liisabotti was permanently shut down in year 2004 and never used since.


More about AI bots and related algorithms:
- https://en.wikipedia.org/wiki/ChatGPT
- https://en.wikipedia.org/wiki/Language_model
- https://en.wikipedia.org/wiki/Transformer_(machine_learning_model)




**Source code**

The original source code was published in 2003 only in PDF format. The author discourages anyone to run the bot in public IRC networks. Additionally, the core module Net::IRC was discontinued in 2004 and the bot is not directly compatible with other IRC libraries.

The bot was written in Perl 5.6 and used the following libraries:
- Net::IRC
- DB_File
- Fcntl
- Term::ANSIColor

They features used from those modules described below:

**Net::IRC**
https://metacpan.org/pod/Net::IRC

Not maintained since 2004. Liisabotti used the following three components:

- Net::IRC - The wrapper for everything else, containing methods to generate Connection objects (see below) and a connection manager which does an event loop on all available filehandles. Sockets or files which are readable (or writable, or whatever you want it to select() for) get passed to user-supplied handler subroutines in other packages or in user code.
- Net::IRC::Connection - The big time sink on this project. Each Connection instance is a single connection to an IRC server. The module itself contains methods for every single IRC command available to users (Net::IRC isn't designed for writing servers, for obvious reasons), methods to set, retrieve, and call handler functions which the user can set (more on this later), and too many cute comments. Hey, what can I say, we were bored.
- Net::IRC::Event - Kind of a struct-like object for storing info about things that the IRC server tells you (server responses, channel talk, joins and parts, et cetera). It records who initiated the event, who it affects, the event type, and any other arguments provided for that event. Incidentally, the only argument passed to a handler function.



**DB_File**
https://perldoc.perl.org/DB_File

DB_File allows access to Berkeley DB files using the tie() mechanism in Perl 5 (for full details, see "tie()" in perlfunc). This facility allows DB_File to access Berkeley DB files using either an associative array (for DB_HASH & DB_BTREE file types) or an ordinary array (for the DB_RECNO file type).


**Fcntl**
https://perldoc.perl.org/Fcntl

This module is just a translation of the C fcntl.h file. Unlike the old mechanism of requiring a translated fcntl.ph file, this uses the h2xs program (see the Perl source distribution) and your native C compiler. This means that it has a far more likely chance of getting the numbers right.

**Term::ANSIColor**
https://metacpan.org/pod/Term::ANSIColor

Color screen output using ANSI escape sequences



**Project website screenshot from 2003**

The website was written only in Finnish language. The site was closed in 2004 and the domain has expired.

[screenshot](liisabotti-website-screenshot-2003-07-09.png)

Copyright 2000-2023 Toni Willberg https://www.linkedin.com/in/toniwillberg/


