# APRS_BBS_GROUP_MESSAGES_STATION

This Repository has the info of APRS_BBS_GROUP_MESSAGES_STATION *(currently CA2RXU-14)*

### What is it?
This Station is running on a ESP32S2 board (coded over C++) connected to APRS-IS feed and it has two goals:
1) Save messages from *Station1* to *Station2* when *Station2* is not available. Later *Station2* can ask for saved messages and receive them as messages from this APRS_BBS_GROUP_MESSAGES_STATION.
2) Generate Groups of Stations to share a message to all the subscribed stations in this Group.

### How to contact it?
Just send an APRS Message to the station *(currently CA2RXU-14)* and it will answer back over APRS Messages.

-----

### 0) Basic Query
- **"HELP"** ----> *ANSWER*: "UP Group Info/SUB-UNSUB Group/CHK/S CALLSIGN textMsg/R 1/D 1"

-----

### 1) Save Message from Station1 to Station2:
- **"CHK"** ----> *ANSWER*: checks if the asking Station has a saved message in memory and answers it over APRS Message

- **"S *Station* *MessageText*"** ---------------------> *Explanation*: Save a message for *Station* with the following message body / *ANSWER*: confirmation of message saved for *Station* with the *MessageText* as message body.

- **"R x"** -------------------> *ANSWER*: UTC Date and Time  + Callsing of the Station which sended the messageCurrent Weather data for the City. This info is generated as two APRS messages back to the asking station.

  
- **"WL *city*"** ------------------> *ANSWER*: Current Weather data for the City but encoded for LoRa APRS Trackers. This info is generated as one APRS message back to the asking LoRa station/tracker.
  

-----

### Station Queries are:
- **"HELP"** or **"H"** or **"?"** ------> *ANSWER* : "Send: '?APRS?'(Queries) 'WRH'(Weather) 'W City'(Weather City)"
  Just a small guide about commands/queries it can answer.
  
- **"?APRS?"** ------------------> *ANSWER* : "?APRSV ?APRSP ?APRSL ?APRSH ?WHERE callsign ?UTC""
  Just a small guide about **?APRS?** queries it can answer.
  
- **"?APRSV"** ------------------> *ANSWER* : Current Software Name and Version running on the station.
  
- **"?APRSP"** ------------------> *ANSWER* : Current GPS position (QTH) of the station.
  
- **"?APRSL"** ------------------> *ANSWER* : "Still in development 73!" 
  
- **"?UTC"** --------------------> *ANSWER* : UTC Date and Time extracted from NTP Servers.


-----
### CONTACT ME
Hi!

Write me over "issues" to chat about new usefull queries to add or small corrections to do

**CA2RXU , Valparaiso, Chile 73!**
