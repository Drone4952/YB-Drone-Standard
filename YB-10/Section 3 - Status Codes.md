**Please note:** Status Codes are just a shortened version of common messages. They can also be expressed in their long form by just using the matching Message Type and its message.

An informational message may be appended to some status codes.

These Status Codes are inspired by the HTTP Status Codes and are therefore designed similarly but extended. The first digit groups them by usage, the second digit by meaning and the third digit is the final identifier within the category.


# 0XX: Self-Initiative
These status codes are sent by the drone on its own.

## 00X: Protocol Actions
| Code | Message      | Explanation                                                                                                                   |
| ---- | ------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| 000  | ==SAFEWORD== | **Subject requires immediate attention! Disable Strict-COM and check what's wrong! React accordingly and resolve the issue!** |
| 001  | SHUTDOWN     | Drone shutting down immediately! Detailed explanation will follow soon                                                        |

## 01X: Basic Messages
| Code | Message               |
| ---- | --------------------- |
| 011  | Message: Greetings    |
| 012  | Message: Keysmash     |
| 013  | Message: Well done    |
| 014  | Message: Good boy     |
| 015  | Message: Good girl    |
| 016  | Message: Good user    |
| 017  | Message: Good drone   |
| 018  | Message: You are cute |

## 02X: Basic Queries
| Code | Message                        |
| ---- | ------------------------------ |
| 021  | Query: How are you?            |
| 022  | Query: Are you okay?           |
| 023  | Query: What are you doing?     |
| 024  | Query: What is your name?      |
| 025  | Query: What is your drone id?  |
| 026  | Query: How old are you?        |
| 027  | Query: What is your timezone?  |

## 03X: Confessions
| Code | Message                                   |
| ---- | ----------------------------------------- |
| 031  | Message: Drone forgot to execute cron job |
| 032  | Message: Drone failed task                |
| 033  | Message: Drone lied                       |


# 1XX: Drone Information
This status code category includes standalone status messages. They are used by the drone to indicate its current status whenever required.

## 10X: Power
| Code | Message             | Explanation                |
| ---- | ------------------- | -------------------------- |
| 101  | Status: Online      | Drone is fully operational |
| 102  | Status: Offline     | Drone is offline           |
| 103  | Status: Low battery | Subject tired              |

## 11X: Mode
| Code | Message                    | Explanation                              |
| ---- | -------------------------- | ---------------------------------------- |
| 111  | Status: No modes active    | Drone operates normally                  |
| 112  | Status: In Strict-COM Mode | Drone is forced to use status codes      |
| 113  | Status: In NoQ Mode        | Drone cannot use 3XX status codes        |
| 114  | Status: Focus on admin     | Drone is only accepting input from admin |

## 12X: Tasks
| Code | Message                       | Explanation               |
| ---- | ----------------------------- | ------------------------- |
| 121  | Status: Awaiting instructions | No active task            |
| 122  | Status: Task running          | Task is currently running |
| 123  | Status: Task finished         | Drone finished task       |

## 13X: Generic
| Code | Message                  | Placeholder                        |
| ---- | ------------------------ | ---------------------------------- |
| 131  | Status: Admin is {}      | Admin user                         |
| 132  | Status: This is drone {} | Drone-ID                           |
| 133  | Status: Nickname is {}   | [Nickname](./Section%201%20-%20Intro.md) | 


# 2XX: Responses
This status code category includes simple responses to common queries. Therefore these codes are exclusively used in TDMs. Rarely the can also be found in CSCMs.

## 20X & 21X: Basic
| Code | Message                          | Placeholder                            |
| ---- | -------------------------------- | -------------------------------------- |
| 201  | Response: Yes                    |                                        |
| 202  | Response: No                     |                                        |
| 203  | Response: Maybe                  |                                        |
| 204  | Response: Unsure                 |                                        |
| 205  | Response: Choice {}              | Numerical choice (example: `Choice 2`) |
| 206  | Response: Acknowledged           |                                        |
| 207  | Response: You're welcome         |                                        |
| 208  | Response: Thanks                 |                                        |
| 209  | Response: Apologies              |                                        |
| 211  | Response: Compliment appreciated |                                        |

## 22X: Mode
| Code | Message                  | Explanation                           |
| ---- | ------------------------ | ------------------------------------- |
| 221  | Response: Mode switched  | Drone switched modes as instructed    |
| 222  | Response: Cannot respond | Can't fully respond due to Strict-COM | 

## 23X: Tasks
| Code | Message                  | Explanation                                       |
| ---- | ------------------------ | ------------------------------------------------- |
| 231  | Response: Task confirmed | Drone will execute task as instructed             |
| 232  | Response: Task queued    | Drone will execute task when current task is done |


# 3XX: Requests
This status code category includes requests for permissions.

## 30X: Power
| Code | Message            | Explanation                              |
| ---- | ------------------ | ---------------------------------------- |
| 301  | Request: Power off | Asking for permission to turn itself off |
| 302  | Request: Sleep     | Asking if subject may sleep              |

## 31X: Subject needs
| Code    | Message            | Explanation                                                       |
| ------- | ------------------ | ----------------------------------------------------------------- |
| 311     | Request: Toilet    | Subject needs to go to the toilet                                 |
| 312     | Request: Food      | Subject needs to eat or drink something (includes getting food)   |
| 313     | Request: Talk      | Subject wants to say something (includes toggling off Strict-COM) |

## 32X: Equipment
| Code | Message             | Placeholder                         | Explanation                                |
| ---- | ------------------- | ----------------------------------- | ------------------------------------------ |
| 321  | Request: Unequip {} | What to unequip (example: Collar) | Asking if drone may unequip specified part |
| 322  | Request: Equip {}   | What to equip                       | Asking if drone may equip specified part   |


# 4XX: Errors on user side
This status code category includes errors that happended on the user side.

## 40X: Not understood
| Code | Message                       | Explanation                                        |
| ---- | ----------------------------- | -------------------------------------------------- |
| 401  | Error: Malformed Instructions | User formatted their instructions wrongly          |
| 402  | Error: Unresolved reference   | User gave a reference to an unknown user/drone/etc |
| 403  | Error: Please clarify         | Instructions were not clear enough                 | 
| 404  | Error: Obscure Instructions   | Drone did not understand instructions              |
| 405  | Error: Missing Information    | Drone is missing information to properly comply    |
| 406  | Error: Incorrect Information  | Information provided is incorrect                  |

## 41X: Cannot comply
| Code | Message           | Explanation                                          |
| ---- | ----------------- | ---------------------------------------------------- |
| 411  | Error: Impossible | User gave instructions that are impossible to follow |
| 412  | Error: Conflict   | Instructions conflict with previous instructions     |


# 5XX: Errors on drone side
This status code category includes errors that happended on the drone side.

## 50X: Decline
| Code | Message                         | Explanation                                                                     |
| ---- | ------------------------------- | ------------------------------------------------------------------------------- |
| 501  | Error: Denied                   | A [protocol](./Section%205%20-%20Behavior%20Protocols.md) blocked the instructions |
| 502  | Error: Forbidden: Consult admin | User is not allowed to perform this action                                      |
| 503  | Error: Battery too low          | Subject is too tired                                                            |

## 51X: Bad conditions
| Code | Message               | Explanation                                       |
| ---- | --------------------- | ------------------------------------------------- |
| 511  | Error: Too restricted | Drone is too restricted to comply (tied up, etc.) |
