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
  - ## Project structure

| File | Purpose |
|------|---------|
| `Login.java` | Registration, validation and login logic |
| `Message.java` | Message creation, ID, hash, arrays, JSON storage and stored-message features |
| `AppChat.java` | Main program: registration, login, QuickChat menu and Stored Messages sub-menu |
| `MessageTest.java` | JUnit tests for Part 2 (length, recipient, hash, ID, send/discard/store) |
| `StoredMessagesTest.java` | JUnit tests for Part 3 (arrays, longest message, search, delete, report) |

## How to run

1. Open the project in NetBeans.
2. Run `AppChat.java` (right-click, then Run File).
3. Register, log in, then enter how many messages you want to send.
4. Use the menu to send, discard or store messages, and option 4 for stored messages.

To run the unit tests, right-click each test file and choose **Test File**.
## Message hash

The hash is made from the first two digits of the message ID, a colon, the message
number, a colon, and the first and last words of the message in capitals.
Example: `00:0:HITONIGHT`
## Storing and reading JSON

Messages are written to `storedMessages.json` with Java's `FileWriter` and read back
with `BufferedReader`. No external library was needed. Libraries such as Gson or
org.json could be used instead.
## Notes and assumptions

- The brief says the recipient number must have "no more than ten characters", but the
  test number `+27718693002` is 12 characters long. We followed the rule from Part 1
  (+27 followed by 9 digits).
- Test message 4 in Part 3 uses the number `0838884567`, which has no international
  code. The unit tests create it directly, but the app would reject it if typed in.
- The sender of each message is the username of the logged-in user.
- Punctuation (such as `?` or `!`) is removed from the first and last words when building the hash.
- The message ID is random, so the tests read the real ID instead of using a fixed value.
- The tests write to `storedMessages.json`, so delete the file before demonstrating the app.

