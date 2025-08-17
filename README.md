# Spring Redis Pub/Sub Implementation

This project demonstrates a simple implementation of the Publish-Subscribe (Pub/Sub) messaging pattern using Spring Boot and Redis. It provides a REST API to publish messages and automatically subscribes to a Redis channel to receive and process those messages.

## 🚀 Features

- **Redis Pub/Sub**: Implements the Publish-Subscribe messaging pattern using Redis as the message broker
- **REST API**: Exposes a simple REST endpoint to publish messages
- **Asynchronous Processing**: Subscribers process messages asynchronously as they arrive
- **Spring Boot**: Built on top of Spring Boot for easy configuration and deployment

## 🛠 Prerequisites

- Java 21 or higher
- Maven 3.6.3 or higher
- Redis Server 5.0 or higher

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Sangramjit786/spring-redis-pubsub.git
cd spring-redis-pubsub
```

### 2. Start Redis Server

Make sure you have Redis server running locally on the default port (6379). If you need to change the Redis configuration, update the `RedisConfig.java` file.

### 3. Build and Run the Application

```bash
mvn clean install
mvn spring-boot:run
```

The application will start on port 9393 (configurable in `application.properties`).

## 🎯 API Endpoints

### Publish a Message

```http
POST /publish
Content-Type: application/json

{
  "id": 1,
  "name": "Sample Product",
  "qty": 10,
  "price": 2999
}
```

**Response:**
```
Event published!!
```

## 🏗 Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/javatechie/redis/
│   │       ├── config/RedisConfig.java    # Redis configuration
│   │       ├── dto/Product.java          # Data transfer object
│   │       ├── publisher/Publisher.java  # Message publisher
│   │       ├── subscriber/Receiver.java  # Message subscriber
│   │       └── SpringRedisPubsubApplication.java  # Main application class
│   └── resources/
│       └── application.properties        # Application configuration
```

## 🔧 Configuration

### Redis Configuration

The Redis connection settings are configured in `RedisConfig.java`. By default, it connects to:
- Host: localhost
- Port: 6379
- Channel: pubsub:javatechie-channel

### Application Properties

- `server.port`: 9393 (default)
- `spring.application.name`: spring-redis-pubsub

## 🧪 Testing

1. Start the application
2. Use a tool like Postman or curl to send a POST request to `http://localhost:9393/publish` with a JSON payload:
   ```json
   {
     "id": 1,
     "name": "Test Product",
     "qty": 5,
     "price": 1999
   }
   ```
3. Check the application logs to see the message being received and processed.


## 📫 Contact

For any queries or suggestions, please open an issue in the GitHub repository.
