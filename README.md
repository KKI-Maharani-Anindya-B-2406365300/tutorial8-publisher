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

![alt text](sending-processing-event.png)
The screenshot above shows both the publisher and subscriber programs running successfully. When I run the publisher using cargo run, the program sends five event messages to the RabbitMQ message broker.
At the same time, the subscriber listens to the broker and receives those messages from the user_created queue. The subscriber then processes each event and displays the user_id and user_name data in the terminal output. This shows that the communication between the publisher, RabbitMQ, and subscriber is working properly.
