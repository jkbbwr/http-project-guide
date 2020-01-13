## Chapter 6: What is a protocol?
How do you think clients and servers talk to each other? 
They need some sort of agreed way to ask for things and to communicate replies or errors. This is 
commonly known as a protocol. We are going to create a really simple protocol for getting and storing strings.

With our hypothetical protocol your server will store the definition to a series of words.
You can do this nice and simply with a map like data structure or something more complex, your choice.

The client will connect and send
```
GET someword
```
All lines in this protocol will be terminated with `\n`

Your server will then look that word up and reply with the value stored against it. 
The server will need to reply with a sensible error message if the word does not exist.

For now the reply will be either
```
ANSWER the description
```
or 
```
ERROR can't find someword
```
We have created a simple reading protocol. This protocol can be extended by adding a new 
```
VERB args go here
```
I encourage you to mess about and add other verb based commands.

## Goals

- Read `GET word` from the client
- Reply `ANSWER definition` to the client
- Give errors on undefined words. `ERROR undefined`

## Bonus goals

- Allow clients to `SET word definition*` at runtime. Where definition might be multiple words ending in `\n`
- Add other commands like `CLEAR` to clear all definitions or `ALL` to get all words currently defined. 

[Back to index.](index.md)