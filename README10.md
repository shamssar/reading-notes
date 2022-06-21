# Event-Driven Programming in Node.js

Event-Driven Programming is a logical pattern that we can choose to confine our programming within to avoid issues of complexity and collision

## Event-Driven Programming makes use of the following concepts:

- An Event Handler is a callback function that will be called when an event is triggered.
- A Main Loop listens for event triggers and calls the associated event handler for that event.

## EventEmitter:
it is allows us to get started incorporating Event-Driven Programming in our project right away
We access the EventEmitter class through the events module. Once imported we’ll need to create a new object from the class to start using it.

> const EventEmitter = require('events').EventEmitter;
const myEventEmitter = new EventEmitter;

> const EventEmitter = require('events').EventEmitter;
const chatRoomEvents = new EventEmitter;

> function userJoined(username){
 
  > alertAllUsers('User ' + username + ' has joined the chat.');
}
chatRoomEvents.on('userJoined', userJoined);

EventEmitter has an emit method that we we use to trigger the event. We would want to trigger this event from within a login function inside of our chatroom module.
> function login(username){
  chatRoomEvents.emit('userJoined', username);
}

## Removing Listeners:
we remove it for this reasons:
* Performance reasons.
* Avoid memory leaks.

to remove event listeners in EventEmitter we can use the removeListener or removeAllListeners method.

> const EventEmitter = require('events').EventEmitter;

>const chatRoomEvents = new EventEmitter;

>function displayMessage(message){

>document.write(message);

}

>function userJoined(username){

>chatRoomEvents.on('message', displayMessage);

>}

>chatRoomEvents.on('userJoined', userJoined);

> //To remove displayMessage function from the message event’s list of handlers

> chatRoomEvents.removeListener('message', displayMessage);


[Event-Driven Programming in Node.js](https://www.digitalocean.com/community/tutorials/nodejs-event-driven-programming)

[Node.js v18.4.0 documentation](https://nodejs.org/api/events.html)

[Home Page](./README.md)