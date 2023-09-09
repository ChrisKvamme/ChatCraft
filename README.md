# ChatCraft
ChatCraft simplifies your AI chat experience. Choose from predefined roles like tech support or financial advisor, input unique details, and start chatting. No more repetitive prompts.

ChatCraftDB: A Real-Time Chat Database
Introduction: ChatCraftDB is a MongoDB database designed to support a real-time chat application. It aims to provide a robust, scalable, and efficient way to store and retrieve chat messages and user information. The database is intended for developers, data analysts, and system administrators who are part of the ChatCraft project.

Schema Design:
  Users Collection
    username: String, unique, required
    email: String, unique, required
    password: String, required
    lastLogin: Date

Messages Collection
    message: String, required
    timestamp: Date, required
    sender: String, required (references Users.username)

Indexes
    Users: Compound index on username and email for faster lookup.
    Messages: Index on timestamp for chronological sorting.

Data Validation:
  Users
    Username and email must be unique to prevent duplicate accounts.
    Password is hashed and stored securely.

  Messages:
    Message content and timestamp are required fields to ensure data integrity.

  Special Configurations:
    Sharding is enabled to distribute data across multiple servers for scalability.
    Replication is set up for high availability and data durability.

  Monitoring:
    We use MongoDB Atlas for real-time monitoring. Metrics like query performance, error rates, and uptime are     tracked.

  Logging:
    Logs are stored in C:\Program Files\MongoDB\Server\7.0\log\mongod.log. These logs are rotated weekly and       can be accessed by system administrators for debugging.

  Optimization:
    Regular checks are performed to analyze query performance.
    Indexes are optimized quarterly based on the query patterns.

Additional Notes:
    To set up the database locally, refer to the setup.md file.
    Backup procedures are outlined in the backup.md file.
