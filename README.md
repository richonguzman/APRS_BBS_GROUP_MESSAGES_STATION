# APRS_BBS_GROUP_MESSAGES_STATION

This Repository has the info of APRS_BBS_GROUP_MESSAGES_STATION *(currently CA2RXU-14)*

### What is it?
This Station is running on a ESP32S2 board (coded over C++) connected to APRS-IS feed and it has two goals:
1) Save messages from *Station1* to *Station2* when *Station2* is not available. Then , when *Station2* is connected, it can ask for saved messages and receive them as messages from this APRS_BBS_GROUP_MESSAGES_STATION.
2) Generate Groups of Stations to share a message to all the subscribed stations in this Group.

### How to contact it?
Just send an APRS Message to the station *(currently CA2RXU-14)* and it will answer back over APRS Messages.

-----

### 0) Basic Query
- **"HELP"** ----> *ANSWER*: "UP Group Info/SUB-UNSUB Group/CHK/S CALLSIGN textMsg/R 1/D 1"

-----

### 1) Messages Queries from Station1 to Station2:
- **"CHK"** ---(*Explanation*: Check if asking Station1 has a message saved) ---> *ANSWER*: Number of saved message in memory.

- **"S *Station2* *MessageText*"** ---(*Explanation*: Save a message from *Station1* to *Station2* with the following message body) ---> *ANSWER*: confirmation of message saved for *Station2* with the *MessageText* as message body.

- **"R X"** ---(*Explanation*: Read message number X from memory for asking *Station1*) ---> *ANSWER*: UTC Date and Time of the saved message  + Callsing of the (other) Station which sended the original message + the body of the message saved.

- **"D X"** ---(*Explanation*: Delete message X from memory for asking *Station1*) ---> *ANSWER*: Confirmation of message X deleted from memory.
  
-----

### 2) Group Messages:
- **"SUB *GROUP1*"** ---(*Explanation*: subscribe asking *Station* to *Group1*) ---> *ANSWER* : Confirmation of subscription to *Group1*.

- **"UNSUB *GROUP1*"** ---(*Explanation*: unsubscribe asking *Station* to *Group1*) ---> *ANSWER* : Confirmation of unsubscription to *Group1*.

- **"UP *GROUP1* *MessageText*"** ---(*Explanation*: update/send *MessageText* to all Stations subscribed to *Group1*) ---> *ANSWER* : "UPDATE *Group1* | *MessageText*"

-----
### CONTACT ME
Hi!

Write me over "issues" to chat about new usefull queries to add or small corrections to do

**CA2RXU , Valparaiso, Chile 73!**
