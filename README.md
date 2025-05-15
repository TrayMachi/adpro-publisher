# Publisher Adpro Module 9
Tristan Agra Yudhistira
2306245112

## Reflection
#### How much data your publisher program will send to the message broker in one run?
It sends 5 UserCreatedEventMessage objects to the message broker in one run. Each message contains:
- user_id (String)
- user_name (String)

The data structure looks like this:
```rust
UserCreatedEventMessage {
    user_id: String,
    user_name: String,
}
```
The program sends 5 different messages with IDs 1-5 and different usernames all prefixed with my own npm "2306245112-".


#### The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Both publisher and subscriber use the URL: `amqp://guest:guest@localhost:5672`

This URL can be broken down into:
- Protocol: `amqp://` - Advanced Message Queuing Protocol
- Credentials: `guest:guest` - Default RabbitMQ username and password
- Host: `localhost` - The message broker is running on the local machine
- Port: `5672` - Standard AMQP port

Using the same URL in both programs ensures they connect to the same message broker instance, enabling communication between the publisher and subscriber through the message queue. Thus the shared configuration ensures both programs connect to the same message broker instance, allowing them to communicate through it.