07 Reading Notes

# Code 301 Reading Notes

## Read 07 API's continued

- A conversation about REST

- Roy Fielding helped to write the first web servers, which send documents across the internet. Roy did a ton of research explaining why the web works and the way it does. Roy's name is on the specification for the protocol that is used to get pages from servers 

- Explaining the web: Roy helped to write HTTP and it is capable of all sorts of neat stuff. If your failure with web pages each page starts with HTTP, which is telling the browser what protocol to use. 

- The web is capable of describing the location of something anywhere in the world from anywhere in the world. HTTP is the foundation of the web, and it is similar to GPS coordinates. 

- All of web is built on an architectural style called REST. Rest provides a definition of a "resource" which is what web pages point to. 

**REST: Representational State Transfer**

- URL's tell a web browser that there is a concept somewhere. A browser can then go ask for specific representation of the concept. Representation is one of those things that does not get used a lot. Most cases a resource has only a single representation and the hope is that representations will be used more in the future.

- For most people there is a concept that is called "Web Services" or "API's". Computers can use the same protocols to send messages back and forth to each other. This has been done for a long time but none of the techniques we use today work well when you need to talk to all the machines in the world.

- When Roy initially built the web, being able to talk to any machine anywhere in the world was a primary concern. The techniques used at work to get computers to talk to each other did not have those requirements, you just talked to small groups of machines.

- Today we need to talk to all the machines about all the stuff that is available. So we need some way of having a machine tell another machine about a resource that might be on five machines down the line. Well in-order to get to that stuff we want faster we use a "redirect" which targets the specific machine to get the information from that computer way down the line.

- The URL has everything that specific computer needs to talk about and the URL matches that. In a way it's like creating a noun that all the computers can use all at the same time. Every programing language, database, or other kind of system has a different way of talking about nouns. This is why a URL is important and allows all of the systems to tell each other about each other's nouns. 

- With the internet nouns are those items we have to go and get, but guess what we need verbs to actually grab that specific noun. A computer will not do a single thing until it's been told to go and get that specific item. There are universal verbs like GET, PUT or DELETE.

- What happens is the user puts in the URL into the webpage, the next thing is the machine has to get that information. In a nutshell a machine has to get stuff and they don't do a lot of other types of interaction with resources. 

- The biggest interaction is how the machine reorganizes the nouns to allow the machine to get what the user has requested. The machine does not care about styling or the information presented to the user, it just looks for a specific item and brings it back. 

- A great example is a school that has all of it's students take test within the computers. Well it would be nice for those test's which are nouns to be located by other computers within the state. Because a bunch of computers are getting information, it gets stored as a noun and then is accessed. The great part is the whole country could set up a bunch of machines to directly access that information each step of the way. 

### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)