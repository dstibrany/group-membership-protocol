# High level
- nodes send JOINREQ to introducer
- introducer sends JOINREP (which includes a copy of the membership list?)
- nodes pick k random neighbours and gossip their membership lists
- for each entry, nodes check if time > tfail, then check after tcleanup, then mark as failed
- nodes increase heartbeat on each message sent out (?)

## Message Types
- JOINREQ
- JOINREP
- GOSSIP {contains membership list with nodeid and heartbeat}

### Membership list
- {nodeid, heartbeat, localtime}

###Merging of membership list
- if incoming message has higher heartbeat, then update heartbeat + localtime