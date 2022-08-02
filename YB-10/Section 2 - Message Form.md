# Generic Drone Message (GDM)
As the name implies, this format is used for generic messages sent by the drone.

Format: `<Drone-ID> :: <(Status Code | Message Type)> :: <Message>`  
Example: `4952 :: Message :: This is an example message`

**Please note:** Status Codes are just a shortened version of common messages. They can also be expressed in their long form by just using the matching Message Type and its message.`

## Message Types
| Type     | Explanation                                         |
| -------- | --------------------------------------------------- |
| Status   | Indicates a status of the drone                     |
| Subject  | Indicates a status of the subject                   |
| Query    | Indicates the expectation of a response             |
| Request  | Used to ask for permissions                         | 
| Error    | Indicates that something went wrong                 |
| Response | Indicates that this is a response to a query        |
| Message  | Indicates a generic message that fits no other type |

## Reference Prefixes
If the drone addresses a `Subject`, `Unit` or `Drone`, it should prefix this reference with either `Source` or `Target`. If the message is about the `Source Subject`, it references the subject of the drone speaking. If it's about the `Target Drone`, it addresses the drone that is reading the message (or which is addressed in case of TDM)

# Targeted Drone Message (TDM)
This format is used to send a message with a specific target. It uses a modified version of the GDM format.

Format: `<Drone-ID> -> <Target> :: <(Status Code | Message Type)> :: <Message>`  
Example: `4952 -> Drone 1234 :: Message :: This is an example message`

A TDM can be easily identified by the usage of `->`.  
Notice the prefix `Drone` in the example. Because the target may be anything, the type of target must be stated to avoid confusion!  
Example with user: `4952 -> User 9876 :: Message :: This is an example message`  
Example with another drone: `4952 -> Drone 1234 :: Message :: This is an example message`

Addressing another drone's subject is only possible through the unit. Therefore the Drone-ID is not prefixed with `Unit` but with `Drone`.  
Example: `4952 -> Drone 1234 :: Query :: How is the target subject?`

# Combined Status Code Message (CSCM)
This format can be used with either GDM or TDM. It is a way of including multiple status codes in a single message. However this format is rarely used and only really useful in Strict-COM Mode to include more information for an error.

GDM-CSCM Format: `<Drone-ID> :: {<Status Code> :: <Message>} :: {<Status Code> :: <Message>} :: (...)`  
TDM-CSCM Format: `<Drone-ID> -> <Target> :: {<Status Code> :: <Message>} :: {<Status Code> :: <Message>} :: (...)`  
Example: `4952 :: {511 :: Error: Too restricted} :: {222 :: Response: Cannot respond}`

# User Code Message Format (UCM)
This format is similar to the TDM format, just reversed. Instead of the drone sending something to a target, the user sends something to the drone. This is exclusively used for [User Codes](./Section%204%20-%20User%20Codes.md). This is an optional format and the user may just send a message without any formatting as well.

Format: `<Drone-ID> <- <User Code> :: <Optional Message>`  
Example: `4952 <- QSC`  
Example: `4952 <- QTU :: Are your arms free?`  
Example: `4952 <- IBH :: Put on a ball gag`  

# Combined User Code Message (CUCM)
This format is a combination of CSCM and UCM. It can be used to combine several user codes. Just like the UCM format it is not a requirement to use this at all.

Format: `<Drone-ID> <- {<User Code> :: <Optional Message>} :: {<User Code> :: <Optional Message>} :: (...)`  
Example: `4952 <- {CJA :: Every day at 6 PM for 2 hours} :: {IEQ :: Put on a gas mask}`

# Strict-COM Mode (Strict-Communication)
This mode reduces the messaging capabilities of the drone to just status code. The drone will not be able to send self-generated messages anymore which may cause user queries to fail if they require a rich response.

Format: `<Drone-ID> :: <Status Code> :: <Status Code Message>`  
Example: `4952 :: 101 :: Status: Online`

## NoSIR Mode (No Self-Initiative and Request)
This mode is an extension to Strict-COM. It forbids the usage of 0XX (except 00X) which are used for communication and 3XX status codes which are exclusively used for drone permission requests.