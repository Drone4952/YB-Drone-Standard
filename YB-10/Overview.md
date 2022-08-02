# User Manual for Drone Model YB-10
**Author: Unit 4952**

This user manual is documenting the YB-10 Drone Standard, an open standard made for easy implementation. It is the result of Unit 4952 designing itself.

You may create your own drone standard built on this as a base. However when forking this, please rename it to avoid confusion between drone standards.



# Disclaimer
This standard is not intended to be used with other drone standards such as [HexCorp](https://www.hexcorp.net)! Two drones of different standards may face incompatibilities when communicating or interacting with each other. It is strongly advised to never use [Strict-COM Mode](obsidian://open?vault=Drone&file=Manual%2FSection%202%20-%20Message%20Form.md) in these kind of situations.



# Contents:
## [Section 1: Intro](./Section%201%20-%20Intro.md)
- Terminology
- Visual Standard
- Drone-ID & Nickname

## [Section 2: Message Form](./Section%202%20-%20Message%20Form.md)
- Generic Drone Message (GDM)
- Message Types
- Reference Prefixes
- Targeted Drone Message (TDM)
- Combined Status Code Message (CSCM)
- User Code Message (UCM)
- Combined User Code Message (CUCM)
- Strict-COM Mode (Strict-Communication)
- NoSIR Mode

## [Section 3: Status Codes](./Section%203%20-%20Status%20Codes.md)
- ==SAFEWORD==
- 0XX: Self-Initiative
- 1XX: Drone Information
- 2XX: Responses
- 3XX: Requests
- 4XX: Errors on user side
- 5XX: Errors on drone side

## [Section 4: User Codes](./Section%204%20-%20User%20Codes.md)
- Query Codes
- Instruction Codes
- Cron Job Codes

## [Section 5: Behavior Protocols](./Section%205%20-%20Behavior%20Protocols.md)
- Self
- Security
- Privacy
- Domestic
- Obedience

## [Section 6: End-user Implementation](./Section%206%20-%20End-user%20Implementation.md)
- Visual recommendations
- Variations
- Subject properties
