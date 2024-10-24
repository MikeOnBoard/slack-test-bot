# **Slack Test Bot**
A simple Slack bot built with Go that allows for testing Slack API interactions and sending messages to Slack channels. The bot listens to events in Slack, including mentions, and responds accordingly, helping developers explore Slack’s messaging API and bot integrations.

## **Project Structure**
```
slack-test-bot/
│
├── main.go
└── README.md
```
## **Features**
- **Slack API Testing**: The bot facilitates testing how Slack messages are handled, focusing on sending messages and responding to mentions.
- **Interactive Messaging**: Works within Slack channels to engage with users dynamically.
- **Socket Mode Support**: The bot connects through Slack's Socket Mode for real-time event handling.
## **Installation and Setup**
### 1. **Clone the Repository**
```bash
git clone https://github.com/MikeOnBoard/slack-test-bot.git
cd slack-test-bot
```
### 2. **Set Up Your Environment**
Ensure that Go is installed on your machine. Then, resolve dependencies by running:
```bash
go mod tidy
```
### 3. **Create a Slack App**
1.Visit the Slack API Dashboard and create a new app.

2.**Enable Socket Mode**:

  - Enable Socket Mode in your app settings to allow real-time event handling.
3. **Event Subscriptions**:
- Subscribe to the necessary bot events, such as:
  - ``app_mention``: Triggered when the bot is mentioned in a message.
  - ``message.channels``: Triggered when a message is posted in a channel where the bot is added.
4. **OAuth & Permissions**:

- Assign the following bot scopes:
  - ``app_mentions:read``
  - ``channels:history``
  - ``channels:read``
  - ``chat:write``
  - ``im:history``
  - ``im:write``
  - ``mpim:history``
  - ``mpim:read``
  - ``mpim:write``
5. Install the app in your workspace and get the bot token.

### 4. **Configure Environment Variables**
Create a ``.env`` file in the project root and include your Slack bot token:

```makefile
SLACK_BOT_TOKEN=xoxb-...
```
### 5. **Run the Application**
To start the bot, run the following command:

```bash
go run main.go
```
### 6. **Interact with the Bot**
You can mention the bot in a channel or send it a direct message to trigger a response:

```css
@slack-test-bot "Hello!"
```
The bot will respond to the mention or message within the channel.

## File Overview
### ``main.go``
- **Purpose**: The core functionality of the Slack Test Bot is contained within this file.
- **Message Handling**: This bot listens for messages in Slack and responds based on pre-defined event triggers.
- **Slack API Integration**: Connects to Slack's API via Socket Mode to process messages and events.
- **Simple Workflow**: A streamlined approach for testing how a Slack bot can send and respond to messages in real time.
### **Key Functions**:
- ``main()``: Initializes the connection to Slack’s Socket Mode, sets up the event handling logic, and listens for incoming messages.
- ``handleMessage()``: Responds to messages mentioning the bot and sends an appropriate response.
- ``sendMessage()``: Sends a message from the bot to a Slack channel.
## Usage Example
Once the bot is set up and running, you can interact with it by mentioning the bot or sending it direct messages:

1.**Mention the bot in a channel**:

```css
@slack-test-bot "Hello!"
```
2.**The bot will respond**:

```css
@user Hello! How can I assist you today?
```
## **Conclusion**
The Slack Test Bot is an excellent tool for developers exploring Slack’s API capabilities. Its lightweight and simple design makes it perfect for testing message-based interactions and developing custom bot functionality in Go. By following this setup, developers can get a hands-on experience with Slack's real-time messaging API and Socket Mode integration, making it an ideal starting point for Slack bot development.