<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./tu_ja.md) | [English](./tu_en.md)

# TidyUp for OPL

Reference video: https://youtu.be/sVmFMCnJf8s

> [!NOTE]  
> This is a sample video from the previous competition. The rules may differ from the rules in this year.

## Main Goal

This task assumes that the robot is tidying up a messy room. The robot will tidy up the room based on information provided in advance about where to place the objects. Then, the robot will move to the next room and provide an object designated in advance from a shelf to a person who is waving (or just raising) its hand. This task is an adaptation of the challenge conducted in [WRS (World Robot Summit) 2020](https://wrs.nedo.go.jp/wrs2020/challenge/download/Rules/DetailedRules_Partner_EN.pdf) for RoboCup JapanOpen @Home OPL.

**Time Limit**: 20 minutes (Task 1: 15 minutes, Task 2: 5 minutes)

## Technical Focus

This task focuses on autonomous navigation in a known environment, object recognition, object grasping, task planning, and so on.

## Settings

- **Location**: The arena environment is based on a household environment. The competition is held in a living room. The arena can be mapped in advance (known environment).
- **Starting location**: The robot starts from outside of the arena and enters the arena when the door is opened.
- **Guests**: Two guests are sitting on chairs, and one of them waving (or raising) its hand receives an object from the robot.

## Scenario

### Starting Phase

1. **Arrangement**: The referee instructs the team to move the robot to the starting position and, according to the referee's instructions, the team arranges the objects to be used. The maximum number of objects that will be used in the `Task 1: Tidy Up Phase` is 10 objects.
1. **Start**: The referee gives the starting signal and starts the timer. At the same time, the team completes the robot starting setup (such as pressing the start button) and leaves the area. Complex setup procedures such as pressing more than two buttons are not allowed. 
1. **Door opening**: One person from the team opens the door at the starting signal. The robot recognizes that the door has opened and autonomously enters the arena.

### Task 1: Tidy Up Phase

1. **Competition time**: The competition time for the `Task 1: Tidy Up Phase` is **15 minutes**.
2. **Tidying up**: After the door is opened, the robot will tidy up all the objects on the table (`Long Table B`). Known and unknown objects are placed in a household-like environment. Each object has a category, and there are designated places (`Long Table A`, `Bin A`, `Bin B`) for each object to be tidied up. The robot will tidy up the objects based on these pre-determined locations.

### Task 2: Delivery Phase

1. **Competition time**: The competition time for `Task 2: Delivery Phase` is **5 minutes**.
1. **Navigation**: The robot will move from one room (`Room 1: Living Room`) to the other room (`Room 2: Dining Room`). **Three dummy obstacles** that will hinder the robot's movement will be set up, and the robot will navigate without making collision with them.
1. **Delivery**: The robot will find and grasp the instructed object from the objects on the shelf and hand it to the person waving (or raising) its hand, who is sitting on the chair.
1. **Goal**: The task ends when the robot hands over the object to the person.

> [!NOTE]  
> Known objects are used as the delivery object. There is a possibility that unknown objects or objects that are not the target may be placed next to the specified objects.

## Objects to manipulate

Please refer to the [Objects](gr_en.md#objects) in the General Rules & Regulations for the objects used in this task.

## Proportion of the objects

- `Standard object` ｜　Announced: 9　→　Used: 6
- `Known object` ｜　Announced: 3　→　Used: 3
- `Unknown object` ｜　Announced: 0　→　Used: 1
- `Dummy object` ｜　Announced: 1　→　Used: 1x3

> [!WARNING]
> The same object will be used for the all teams in the same trial. The different object will be used for the different trials.

## Object Category and Placement Goal

> [!NOTE]
> Updating. Furniture name may be updated.

The placement locations for each object category are as follows:
<div align="center"><img src="./tu_layout.jpg" width="70%"></div>
<br>

## Restart

The following action is admitted when the robot restarts.

- The team can remove the object that the robot grasps (put out of the arena) when the team declares restart.
- The team can rearrange the objects when the robot waiting at the start position (the team can rearrange fallen or dropped objects into the initial position).

## Deus ex Machina

The following Deus ex Machina will be adopted in this task. With Deus ex Machina, although no points are awarded for the corresponding action, it is possible to skip partial tasks with simpler methods and continue with the overall task.

|Action|Bypassing|
|------|---------|
| Object grasping | Referee holds the object instructed by the robot and gives it to the robot (or places it in a specific location). At this time, the robot needs to accurately convey the object's position, name, instructions, etc to the referee |
| Object placement | Referee places the object that the robot is holding (or is in a specific location) in the location specified by the robot. At this time, the robot needs to accurately convey the object's placement position, name, instructions, etc to the referee |
| Object delivery | The guest receives the object that the robot is holding (or is in a specific location) without being handed over by the robot. At this time, the robot needs to accurately convey the guest's location, object name, instructions, etc to the referee |


## Score Sheet

| Action                                                                           | Score |
| -------------------------------------------------------------------------------- | ----- |
| **Task 1: Tidy Up Phase**                                                        |       |
| Tidying up objects                                                               |       |
| &nbsp;&nbsp;Grasping objects (10 points per item)                                | 10x10 |
| &nbsp;&nbsp;Transporting and placing/storing objects (10 points per item)        | 10x10 |
| &nbsp;&nbsp;Placing/storing objects in the correct location (15 points per item) | 15x10 |
| **Task 2: Delivery Phase**                                                       |       |
| Enter `Room 2: Dining Room` without colliding with any obstacle                  | 30    |
| Object Delivery                                                                  | 30    |
| Grasping food item from the shelf                                                | 30    |
| Grasping the instructed food item from the shelf                                 | 30    |
| Handing over the item to a person                                                | 30    |
| Handing over the item to the person waving (or raising) its hand                 | 30    |
| Penalty                                                                          |       |
| Non-participation (without previous instance)                                    | -500  |
|                                                                                  |       |
| Total (including bonus tasks)                                                    | 500   |


**Score Sheet**: [RCJ2023 OPL Tidy Up Score Sheet v1](https://docs.google.com/spreadsheets/d/1Dn0LTINAVYMcSL2Yoqi4iicPZOmU6h8e/edit?usp=sharing&ouid=115914283332872721627&rtpof=true&sd=true)


## Instructions from the Executive Committee (EC)

- Preparation (several days to several weeks before the competition)
  - Prepare for known and unknown objects.
- Announcements (Before the task starts)
  - Select two guests
- Announcements (30 minutes before the task starts)
  - Select and announce the initial position of the objects.
  - Select and announce the unknown object.

## Role of the scorer

- Gather 30 minutes before the competition, receive instructions, and receive the score sheet.
- Act as the referee as described during the task.
- Score the competition.
- Verify scoring content with other TCs.
- Submit the score sheet.

> [!NOTE]  
> Scorers are selected from each team and score other team's task. Please refer to the [Scoring System](./gr_en.md#scoring-system).
