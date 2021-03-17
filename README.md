# Programming in Depth – Exercise 3 – Web Services 

#### Recommended reading
- [General asynchronous programming concepts](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Concepts)
- [axios](https://github.com/axios/axios)
- [Promise - MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- [Promise - javascript.info](https://javascript.info/promise-basics)
- [async/await](https://javascript.info/async-await)
- [Sending JavaScript Http Requests with Axios](https://www.youtube.com/watch?v=qM4G1Ai2ZpE)

You have about 5 kids at home (for those of you who don't, you can just imagine it). And as with all kids they love 
[Pokémon](https://en.wikipedia.org/wiki/Pok%C3%A9mon) and
since they know you are a programming expert (if you're not, just imagine this as well) they have asked you to create an 
application where they can look up different pokemons.

In this case, your program is going to need access to data about pokemons and you could create that data yourself manually, for
example in a text file or in an SQL database, but that would take quite some time. It would be much more convenient to use an
existing one that someone else is maintaining. A way to solve this is by using a web service which provides the necessary data. 

### Web services
A web service is an application that can be communicated with through the web via a standard protocol (HTTP/HTTPS etc.) and is
usually designed to communicate with other programs rather than humans. What does this mean? Take an example from
[Meta Weather](https://www.metaweather.com/), a website for checking the weather. If we want to check the weather in
London on the 4th of April 2013 we can do it the "normal" way:

https://www.metaweather.com/44418/2013/4/27/

or we could access the same data via their webservice:

https://www.metaweather.com/api/location/44418/2013/4/27/

As you can see, we can conlude the following:
- The first one is more human-readable.
- The second one is raw JSON which will be easier to handle in a program.
- The weather in England always has been and always will be utterly disappointing.

Note that we can see what protocol is being used from the first part of the link(https). Although there are many other protocols as well, we will be focusing on HTTP/HTTPS in this lab.

#### Exercises
You are to create a JavaScript application with a text interface (see [here](https://nodejs.org/en/knowledge/command-line/how-to-prompt-for-command-line-input/) how to take in user input) which will act as a small pokemon encyclopedia (aka. a 
[pokedex](https://bulbapedia.bulbagarden.net/wiki/Pok%C3%A9dex)). You should use the web service API given at [PokéAPI](https://pokeapi.co/) to collect the Pokémon data. You should be able to do the following:


1. Enter a name of a pokémon and get the id, name, height and weight
1. Enter a name of a location and get all the names of the location in different languages (the ones that are available in the response) and the name of the region it is in.
1. Each pokémon has a [type](https://bulbapedia.bulbagarden.net/wiki/Type) (grass, water etc.). Each type has its strength and weaknesses, for example water types are super effective against fire types. Add more information to the pokémon lookup so that you can also show the pokémon type and list the type weaknesses and strengths respectively.

How you present the application is all up to you as long as it's user-friendly.

#### Tips
Although not strictly necessary, it is recommended to use the axios package for making HTTP requests.

### Requirements
- Pokemon data must be collected from the PokéAPI
- The application must be text based. If you want to create a graphical version you should complete the text based version first. You can then add the graphical version as an extra assignment.
- Tests are not a strict requirement this assignment as they can be a bit difficult (but not impossible) to implement on programs that make network-related requests to other servers. To test API calls, you need to do some [mocking](https://dev.to/endymion1818/how-to-test-javascript-api-calls-187k). Feel free to make tests for the parts that you know :) 

### Discussion
Every time we're communicating with a server using the HTTP/HTTPS protocol we use a so-called [request method](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods). If you go to the link, you can see that there are several methods for different situations. Try to answer the following:

1. Which one(s) are you using in your implementation? 
1. Based on what you are communicating to the web service, do you think that the request method is appropriate? Why/Why not?

## Further reading
- [Hypertext Transfer Protocol (HTTP/1.1) Semantics, request methods](https://tools.ietf.org/html/rfc7231#section-4)
