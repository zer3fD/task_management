# TaskManagement


### **Project Overview**

Develop a web application where teams can manage tasks collaboratively in real-time. Users can create projects, assign tasks, comment on tasks, and see updates instantly. The application will include:

- **User Authentication and Authorization**
- **Real-time Features**
- **Background Jobs**
- **Data Encryption and Key Rotation**
- **Audit Logging**
- **Testing and Deployment**

---

### **Key Features to Implement**

#### **1. User Authentication and Authorization**

- **User Registration and Login**:
  - Implement using `mix phx.gen.auth`.
  - Secure password storage and authentication flow.
- **Email Verification**:
  - Send verification emails asynchronously using background jobs.
- **Password Reset Functionality**:
  - Allow users to reset passwords securely.
- **Role-Based Access Control**:
  - Define roles (Admin, Manager, User).
  - Restrict access to certain features based on roles.

#### **2. Real-time Task Management**

- **Task Creation and Assignment**:
  - Users can create tasks with details like title, description, due date.
  - Assign tasks to team members.
- **Real-time Updates**:
  - Use **Phoenix LiveView** or **Phoenix Channels** to broadcast updates.
  - Instantly reflect changes across all connected clients.
- **Comments and Collaboration**:
  - Allow users to comment on tasks.
  - Real-time comment updates.
- **Presence Tracking**:
  - Show online/offline status of users.
  - Display who is currently viewing or editing a task.

#### **3. Background Jobs**

- **Email Notifications**:
  - Use **Oban** to send emails when tasks are assigned or updated.
  - Handle email verifications and password resets asynchronously.
- **Reminders and Alerts**:
  - Schedule reminders for upcoming task deadlines.
  - Send daily or weekly summaries.
- **Data Processing**:
  - Offload heavy computations or data exports to background jobs.

#### **4. Data Encryption and Key Rotation**

- **Sensitive Data Encryption**:
  - Use the **Cloak** library to encrypt sensitive fields like personal information.
- **Key Rotation**:
  - Implement key rotation strategies to update encryption keys periodically.
  - Handle decryption of data encrypted with old keys using tagged ciphertext.
- **Secure Key Management**:
  - Store keys securely using environment variables or a secrets manager.
  - Implement versioning for keys.

#### **5. Audit Logging**

- **Track User Actions**:
  - Log actions like task creation, updates, deletions, and assignments.
- **Immutable Logs**:
  - Ensure audit logs are tamper-proof and immutable.
- **Timestamp and User Identification**:
  - Record when an action occurred and who performed it.
- **Efficient Querying**:
  - Design the database schema to allow efficient retrieval and analysis of logs.

#### **6. Testing and Quality Assurance**

- **Unit and Integration Tests**:
  - Write tests for all critical components.
- **Testing Background Jobs**:
  - Ensure jobs are enqueued and executed as expected.
- **Encryption Tests**:
  - Test encryption and decryption processes, including key rotation.
- **Real-time Features Testing**:
  - Simulate multiple users to test real-time updates and presence.


To start your Phoenix server:

  * Run `mix setup` to install and setup dependencies
  * Start Phoenix endpoint with `mix phx.server` or inside IEx with `iex -S mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Learn more

  * Official website: https://www.phoenixframework.org/
  * Guides: https://hexdocs.pm/phoenix/overview.html
  * Docs: https://hexdocs.pm/phoenix
  * Forum: https://elixirforum.com/c/phoenix-forum
  * Source: https://github.com/phoenixframework/phoenix
