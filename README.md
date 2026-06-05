# How to Run the Application

## Prerequisites

- Docker
- Visual Studio 2022 (or later)
- .NET SDK

## Step 1: Start RabbitMQ

Run the following command to start RabbitMQ with the Management UI enabled:

```bash
docker run -it --rm --name rabbitmq \
-p 5672:5672 \
-p 15672:15672 \
rabbitmq:3.12-management
```

RabbitMQ Management UI will be available at:

- URL: http://localhost:15672
- Username: `guest`
- Password: `guest`

## Step 2: Configure Startup Projects

Open the solution in Visual Studio and configure all required projects as startup projects:

1. Right-click the solution in **Solution Explorer**.
2. Select **Properties**.
3. Navigate to **Startup Project**.
4. Choose **Multiple Startup Projects**.
5. Set all required projects to **Start**.

## Step 3: Run the Backend Services

Press **Ctrl + F5** to start all backend services without debugging.

## Verify the Application

- Ensure all backend services start successfully.
- Verify that RabbitMQ is running by opening http://localhost:15672.
- Check the application logs for any startup errors.

## Notes

- RabbitMQ must be running before starting the backend services.
- If port `5672` or `15672` is already in use, stop the conflicting service or update the port mappings accordingly.
- The RabbitMQ container will be automatically removed when stopped because the `--rm` flag is used.
