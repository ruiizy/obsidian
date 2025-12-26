## Types of APIs
- __REST__: Representational State Transfer, this APIS use http transfer and the object JSON.
	- **Resources (The "R")**: In REST, everything is considered a "resource". A resource is just an object or a piece of data (like a user, a photo, a product, or a tweet).
	- **Representation**: When you ask the server for a resource, it doesn't send you the actual database file. It sends you a _representation_ of the data, usually in a format like **JSON** or XML.
	- **State Transfer**: If you modify data (like updating your profile picture), you are transferring a new "state" to the server. Conversely, when you download a picture, the server transfers the state of that picture to your device
- **SOAP**: Alternative to REST, usually legacy or enterprise XML
- **GraphQL**: This APIS don't interactive directly on BBDD, frontend provides query.
- **gRPC**:Remote procedure Call
	- **RPC**: execute things on BE
- **WebSocket**: Bidirectional  communication frontend and backend usually use on real time apps, use on chats, notifications, etc..
## RESTful API
#### The golden Rules
For an API to be truly "RESTful". it must follow several constraints. The two most important ones are: 
##### Statelessness
Every single request you send to the serve must contain all the information needed to understand and process that request (incluiding who you are, usually via an authentication token). The server treats every request as if it's meeting you for the first time.
- *Benefits*: This makes the server verty fast and easy to scale because it doesn't have to hold onto memory sessions for thousand of users.
##### Client-Server Separation
The interface (Client/Frontend) and the data storage (Server/Backend) are completely independent.
- You can change the code on the server without breaking the iPhone app, as log as the way they talk (the API structure) stays the same.

#### 
- http methods
- endpoints
- http responses
- JSON
#### NOTES

When an API follows these rules, its called a __RESTful API__.
