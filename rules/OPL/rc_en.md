<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./rc_ja.md) | [English](./rc_en.md)

# Receptionist

Reference video: https://youtu.be/p9ki89buY68

> [!NOTE]  
> This is a sample video for reference and the task content may differ depending on the RoboCup rules.
> Questions and discussions is accepted on GitHub [Issues](https://github.com/RoboCupAtHomeJP/Rule2023/issues).

> [!NOTE]  
> This rule is based on the RoboCup JapanOpen 2023 referring the Receptionist of RoboCup 2022. The score sheet is based on RoboCup JapanOpen 2022.

## Main Goal

In this task, the robot works as a receptionist and guides guests arriving at the venue to the living room. The robot asks the guests for their names and favorite drinks and introduces them to the host. Additionally, the robot offers empty seats to newly arrived guests.

## Focus

System Integration, Human-Robot Interaction, Person Detection, Person Recognition

## Setup

- **Starting Point**: The robot starts from a predetermined location inside the arena.
- **Host**: The name of the host is John.
- **Guests**: Both guests have a name and favorite drink. The arriving guests will come in front of the robot. The two guests will arrive separately.

> [!NOTE]  
> Information such as name lists and starting points will be published in the following repository by the setup day.
> https://github.com/RoboCupAtHomeJP/AtHome2023/opl

## Scenario

1. Start Phase
   1. **Game Time**: The time limit is **seven minutes**.
   2. **Setup**: The TC instructs the team to move the robot to the starting position.
   3. **Start**: The TC gives the start signal and starts the timer. The team completes the final simple setup (pressing the start button, etc.) and leaves the area. No complex setup procedures are allowed, such as pressing two or more buttons.
2. Reception Phase
   1. **Detection**: The robot detects guests who arrive and enter the room.
   2. **Reception**: The robot asks for the guest's name and favorite drink. If the robot cannot understand the name or favorite drink, the robot can request the guest to repeat the question.
   3. **Introduction**: The robot introduces the arrived guest to the host. The robot points to the person being introduced and introduces their name and favorite drink.
3. Guidance Phase
   1. **Guiding**: The robot shows the guest to an empty seat and seats them. The robot points to where the guest can sit (an empty seat).
   2. **Seat Swapping**: The guest in the living may change seats.
4. Bonus Phase
   1. The robot can earn bonus points by describing four features (e.g. clothing color, hair color, gender, age) of the first guest to the second guest.

When the robot interacts with a human, the robot needs to pay attention to the person interacting with it. For example, the robot can point to one person and face the other while talking or alternately gaze between two people.

## Deus ex Machina

The following Deus Ex Machina can be used for this task. By using Deus ex Machina, points for the corresponding actions are not scored but actions can be skipped more easily with simpler methods to continue the task.

| Action | Bypassing |
| ------ | --------- |
| Human detection | Identify human(s) by using marker(s) |
| Detecting empty seats | Identify empty seats by placing markers on them |

## Score sheet

| Action | Score |
| ------ | ----- |
| **Main Task** |   |
| Introduce the first guest to the host             |  |
| &emsp; Introduce the name of the first guest        | $25$ |
| &emsp; Introduce the favorite drink of the first guest | $25$ |
| &emsp; Direct attention toward the first guest during introduction   | $35$ |
| Guide the first guest to the empty seat         |  |
| &emsp; Detect an empty seat                    | $60$ |
| &emsp; Point or face the empty seat for the first guest              | $65$ |
| Introduce the second guest to the host            |  |
| &emsp; Introduce the name of the second guest       | $25$ |
| &emsp; Introduce the favorite drink of the second guest | $25$ |
| &emsp; Direct attention toward the second guest during introduction   | $35$ |
| Guide the second guest to the empty seat         |  |
| &emsp; Detect an empty seat                    | $60$ |
| &emsp; Point or face the empty seat for the second guest              | $65$ |
| **Bonus Task**                            |   |
| Describe the four features of the first guest        | $4 \times 20$ |
| **Deus Ex Machina** |  |
| &emsp; Direct attention by detecting human(s) using marker(s) | $-17.5$ |
| **Penalty**                            |   |
| &emsp; Restart | Score earned right after the restart $\times -0.5$|
| &emsp; Not attending (absence without permission)                      | $-500$  |
| **Total**                                  | $500$ |

## Instructions by TC

- Preparation
  - Assign names and drinks to three volunteers.
  - Place (replace) people in the living room.
- Announcements (Setup Day)
  - Publish the starting point of the task and the host's location.
  - Publish the name and drink list.

## Referee Movement

Referees selected according to the General Rules will perform the following.

- 30 minutes before the start of the competition, receive instructions, a score sheet and a command list.
- Act as the referee described in the scenario.
- Score the competition.
- Verify the score with other referees and TC.
- Submit the score sheet to TC.
