a. How much data your publisher program will send to the message broker in one run?
In one run, the publisher program sends five messages to the message broker. Each message contains a user_id and a user_name. This happens because the program calls publish_event() five times with different user data, so the broker receives a total of five event messages in a single execution.

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean? 
The URL is the connection address used by both the publisher and subscriber to communicate with the same RabbitMQ message broker. Since both programs use the exact same URL, it means they are connected to the same broker service running on the local machine.
In the URL:
- guest is the username
- guest is the password
- localhost means the broker is running on the same computer
- 5672 is the default AMQP port used by RabbitMQ
Using the same connection URL allows the publisher to send messages and the subscriber to receive those messages through the same broker.

![alt text](<Running RabbitMQ .png>)