# Final-prog-poe
# QuickChat

A console-based chat application written in Java (NetBeans). Users register,
log in, then send, discard or store messages, and can manage their stored messages.

**Module:** [module name and code]
**Student(s):** [names and student numbers]
**Date:** November 2026

## Features

### Part 1: Registration and login
- Username must contain an underscore and be no more than 5 characters
- Password must have at least 8 characters, a capital letter, a number and a special character
- Cell number must start with +27 followed by 9 digits
- Login only succeeds with the registered username and password

### Part 2: Sending messages
- "Welcome to QuickChat" message and a numeric menu
- The user chooses how many messages to enter when the app starts
- Each message has an auto-generated 10-digit ID, a message number, a recipient, the text and a message hash
- Messages are limited to 250 characters
- For each message the user can Send, Disregard or Store it
- The total number of messages sent is displayed at the end

### Part 3: Arrays and stored messages
- Arrays (ArrayLists) are filled while the program runs, with no hard-coded data:
  Sent Messages, Disregarded Messages, Stored Messages, Message Hashes and Message IDs
- Stored messages are saved to `storedMessages.json` and read back into the Stored Messages array when the app starts
- Menu option 4, "Stored Messages", lets the user:
  - a. Display the sender and recipient of all stored messages
  - b. Display the longest stored message
  - c. Search for a message ID and display the recipient and message
  - d. Search for all stored messages for a particular recipient
  - e. Delete a message using its message hash
  - f. Display a report of the full details of all stored messages
