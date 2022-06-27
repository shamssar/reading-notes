#  Message Queues
Socket.io Chat Example
 a basic chat application is created where there is a bi-directional communication channel between a client and a server.

Broadcasting is for us to emit the event from the server to the rest of the users. io.emit('someEvent',payload).

To send a message to everyone except for a certain emitting socket, we have the broadcast flag for emitting from that socket:

io.on('connection', (socket) => {
  socket.broadcast.emit('hi');
});
----------------------------------------------------------------------------------------------------------
## Rooms:
is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of clients:


![image](./screenhoots/room.png)

Please note that rooms are a server-only concept (i.e. the client does not have access to the list of rooms it has joined).

### To join room:

You can call join to subscribe the socket to a given channel:

> io.on("connection", (socket) => {
  socket.join("some room");
});

### Emitting/Broadcasting: to/in
> io.to("room1").to("room2").to("room3").emit("some event");

Or from a given socket:

> io.on("connection", (socket) => {
  socket.to("some room").emit("some event");
});

### To leave a room: leave() just like join()

### Disconnection
> io.on("connection", socket => {
  socket.on("disconnecting", () => {
    console.log(socket.rooms); // the Set contains at least the socket ID
  });

  >socket.on("disconnect", () => {
    // socket.rooms.size === 0
  });
});

## Namespaces
A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called "multiplexing").
![image](./screenhoots/namespace.png)

Each namespace has its own:
* event handlers
> io.of("/orders").on("connection", (socket) => {
  socket.on("order:list", () => {});
  socket.on("order:create", () => {});
});

> io.of("/users").on("connection", (socket) => {
  socket.on("user:list", () => {});
});
* rooms
>const orderNamespace = io.of("/orders");

>orderNamespace.on("connection", (socket) => {
  socket.join("room1");
  orderNamespace.to("room1").emit("hello");
});

>const userNamespace = io.of("/users");

>userNamespace.on("connection", (socket) => {
  socket.join("room1"); // distinct from the room in the "orders" namespace
  userNamespace.to("room1").emit("holà");
>});

* middlewares

>const orderNamespace = io.of("/orders");
orderNamespace.use((socket, next) => {
  // ensure the socket has access to the "orders" namespace, and then
  next();
});

>const userNamespace = io.of("/users");
userNamespace.use((socket, next) => {
  // ensure the socket has access to the "users" namespace, and then
  next();
});


### Main namespace is: /
> io.emit("hello"); is actually equivalent to io.of("/").emit("hello");. io.sockets is an alias for io.of("/").

### Multiplexing will be disabled in the following cases:
* Multiple creation for the same namespace.
>const socket1 = io();
const socket2 = io(); // no multiplexing, two distinct WebSocket connections
* Different domains.
>const socket1 = io("https://first.example.com");
const socket2 = io("https://second.example.com"); // no multiplexing, two distinct WebSocket connections
* Usage of the forceNew option
>const socket1 = io();
const socket2 = io("/admin", { forceNew: true }); // no multiplexing, two distinct WebSocket connections
* Dynamic namespaces
>io.of(/^\/dynamic-\d+$/);
Existing namespaces have priority over dynamic namespaces.

### The return value of the of() method is what we call the parent namespace, from which you can:
* Register middlewares.
>const parentNamespace = io.of(/^\/dynamic-\d+$/);
parentNamespace.use((socket, next) => { next() });
* Broadcast events.
>const parentNamespace = io.of(/^\/dynamic-\d+$/);
parentNamespace.emit("hello"); // will be sent to users in /dynamic-1, /dynamic-2, ...



References:

[Socket.io Chat Example](https://socket.io/get-started/chat/)

[Rooms](https://socket.io/docs/v4/rooms)

[Namespaces](https://socket.io/docs/v4/namespaces/)

[Socket.io Emit Cheatsheet](https://socket.io/docs/v4/emit-cheatsheet/)

[Home page](./README.md)