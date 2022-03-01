#dictionary #development_career 
# WebSocket
A protocol for persistent bidirectional connections between client and server.

The conuterpart of WebSockets were long-polling HTTP connections. They are not prefferred, because they exhaut the server resources keeping the connection even when there are no data flow.  
First, the client will send an HTTP request for a WebSocket connection and wait for a positive response. Once this handshake is completed, data will flow until both parties agree that the connection should be closed. 