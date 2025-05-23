# CRDT Server Overview

This document provides an overview of how to use the CRDT server in the Constellation project.

## How to use the CRDT server

1. **Start the CRDT server**: The CRDT server is a separate process that needs to be started before you can use it. You can start the server by running the following command:

2. **Set the room name**: The CRDT server uses rooms to organize data. You need to set the room name before you can use the server. You can set the room name using the following code:

   ```js
    // The room name should be formed as: postgres/<constellation_uuid>/<file_uuid> or neo4j/<constellation_uuid>/<node_uuid>/<attribute_name>
    // For example, if you are using PostgreSQL and your constellation UUID is "1234" and your file UUID is "5678", the room name would be:
    const roomname = `postgres/1234/5678`
    // If you are using Neo4j and your constellation UUID is "1234", your node UUID is "5678", and your attribute name is "story", the room name would be:
    const roomname = `neo4j/1234/5678/story`
   ```

3. **Install the Yjs library**: The CRDT server uses the Yjs library to handle the synchronization of data. You need to install the Yjs library in your project. You can install it using npm:

   ```bash
    npm install yjs y-websocket
   ```

4. **Import the Yjs library**: Once you have installed the Yjs library, you need to import it in your project. You can import it using the following code:

   ```js
    import * as Y from 'yjs'
    import { WebsocketProvider } from 'y-websocket'
   ```

5. **Create a Yjs document**: You need to create a Yjs document to hold your data. You can create a Yjs document using the following code:

   ```js
    const ydoc = new Y.Doc()
   ```

6. **Set the JWT token**: The CRDT server requires a JWT token to authenticate the user. You can set the JWT token in the `Authorization` header of the WebSocket connection. You can use the following code to set the JWT token:

   ```js
    const jwt = // get the JWT token from your authentication system
    document.cookie = `Authorization=${jwt};`
   ```

7. **Connect to the CRDT server**: Once the server is running, you can connect to it using a WebSocket client. The server listens on the following URL:

   ```js
    const provider = new WebsocketProvider(
        'ws://localhost:8003', // use the public ws server
        roomname,
        ydoc
    )
   ```

8. **Use the CRDT server**: Once you are connected to the server, you can use it to synchronize your data. The CRDT server uses the Yjs library to handle the synchronization of data. You can use the Yjs API to manipulate your data and the CRDT server will take care of synchronizing it with other clients.

9. **Handle events**: The CRDT server emits events when data is synchronized. You can listen to these events to update your UI or perform other actions. For example, you can listen to the `update` event to get notified when data is updated:

   ```js
    ydoc.on('update', (update) => {
        console.log('Data updated:', update)
    })
   ```

10. **Handle errors**: The CRDT server may emit errors if there are issues with the connection or synchronization. You can listen to the `error` event to handle these errors:

   ```js
    // Handle errors
    provider.ws.addEventListener('close', ev => {
        if (ev.code === 4401) {
            console.warn('Invalid token, I stop the reconnection attempts');
            // Deactivate the connection
            provider.disconnect();
        }
        if (ev.code === 4403) {
            console.warn('Invalid URL, I stop the reconnection attempts');
            // Deactivate the connection
            provider.disconnect();
        }
    });

    provider.on('connection-error', () => {
        // If a protocol error occurs, the connection will be closed
        provider.ws.close();
        provider.disconnect();
    });
   ```
