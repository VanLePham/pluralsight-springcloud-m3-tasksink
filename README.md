## pluralsight-springcloud-m3-tasksink
Enable task launcher

Create a simple task sink, connect to Spring Cloud Stream Rabbitmq (See Spring Cloud Task annotation `@EnableTaskLauncher`, and Spring Cloud Stream Rabbit for more details)

See the `application.properties` for the rabbitmq setup

To test the sink, need to have Rabbitmq server running. You can download and install Rabbitmq in your machine, or using Rabbitmq docker or vagrant. 
To install Rabbitmq in Mac using homebrew:
  $`brew update`
  $`brew install rabbitmq`
  $`export PATH=$PATH:/usr/local/sbin`

Need to insall rabbitmq management console plugin to view the queue:
  $`rabbitmq-plugins enable rabbitmq_management`

Start Rabbitmq server:
  $`rabbitmq-server`
  
Open web browser: http://localhost:15672/#/queues to view the queues in the rabbitmq manager console. It should not have any queue for now. 

Build the project and run the app. If there is no errors, you should see a queue in the rabbitmq manager console, something like `tasktopic.anonymous.tu-xxxxx....` (because I set the `spring.cloud.stream.bindings.input.destination` in the `application.properties` as `tasktopic`)

