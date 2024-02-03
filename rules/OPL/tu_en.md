<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./tu_ja.md) | [English](./tu_en.md)

# TidyUp for OPL

Reference video: https://youtu.be/sVmFMCnJf8s

> [!NOTE]  
> The reference video is not perfect. The task may differ depending on the rules of each year RoboCup, so please use it as a reference only. If you have any concerns or points you would like to discuss, please write them in the [Issues](https://github.com/RoboCupAtHomeJP/Rule2023/issues) section of GitHub.


## Main Goal

This task assumes that the robot is tidying up a messy room. The robot will tidy up the room based on information provided in advance about where to place the objects. Then, the robot will move to the next room and provide an object designated in advance from a shelf to a person who is waving (or just raising) its hand. This task is an adaptation of the challenge conducted in [WRS (World Robot Summit) 2020](https://wrs.nedo.go.jp/wrs2020/challenge/download/Rules/DetailedRules_Partner_EN.pdf) for RoboCup Japan Open @Home OPL.

**Time Limit**: 20 minutes (Task 1: 15 minutes, Task 2: 5 minutes)

## Technical Focus

This task focuses on autonomous navigation in a known environment, object recognition, object grasping, task planning, and so on.


## Settings

- **Location**: The arena environment is based on a household environment is used. The competition is especially held in a living room. The arena can be mapped in advance (known environment).
- **Starting location**: The robot starts from outside the arena and enters the arena when opening the door.
- **Guests**: Two guests are sitting on chairs, and one of them waving (or raising) its hand receives an object from the robot. Please select two guests from your team.


## Scenario

### Starting Phase

1. **Competition time**: The competition time is a total of **20 minutes**, with 15 minutes for the `Task 1: Tidy Up Phase` and 5 minutes for the `Task 2: Delivery Phase`.
1. **Arrangement**: The referee instructs the team to move the robot to the starting position and, according to the referee's instructions, the team arranges the objects to be used. The maximum number of objects that will be used in the `Task 1: Tidy Up Phase` is 10 objects.
1. **Start**: The referee gives the starting signal and starts the timer. At the same time, the team completes the robot starting setup (such as pressing the start button) and leaves the area. Complex setup procedures such as pressing more than two buttons are not allowed. 
1. **Door opening**: One person from your team opens the door at the starting signal. The robot recognizes that the door has opened and autonomously enters the arena.

### Task 1: Tidy Up Phase

1. **Competition time**: The competition time for the `Task 1: Tidy Up Phase` is **15 minutes**.
1. **Tidying up**: After the door is opened, the robot will tidy up all the objects on the table (`Long Table B`). Known and unknown objects are placed like a household environment. Each object has a category, and there are designated places (`Long Table A`, `Bin A`, `Bin B`) for each object to be tidied up. The robot will tidy up the objects based on these pre-determined locations.

### Task 2: Delivery Phase

1. **Competition time**: The competition time for `Task 2: Delivery Phase` is **5 minutes**.
1. **Navigation**: The robot will move from one room (`Room 1: Living Room`) to the other room (`Room 2: Dining Room`). **Three dummy obstacles** that will hinder the robot's movement will be set up, and the robot will navigate without making collision with them.
1. **Delivery**: The robot will find and grasp the instructed object from the objects on the shelf and hand it to the person waving (or raising) its hand, who is sitting on the chair.
1. **Goal**: The task ends when the robot hands over the object to the person.

> [!NOTE]  
> Known objects are objects that have been publicly announced in advance. However, there is a possibility that unknown objects or objects that are not the target may be placed next to the specified objects, so please be careful.


## Objects to manipulate

For the `Tidy Up for OPL` task, the list of nine objects used in RCAP2021 will be used. You can check the object list from the link below, which includes photos, official names, and object categories (for example, `Noodle` belongs to the `Food` category). Most objects are lightweight and easy for the robot to grasp. The location where each object should be placed or tidied up is determined for each category of object. By referring to these categories, the robot will find and tidy up the objects during the competition. Please note that modifing the objects is prohibited.

In the competition task, objects will be used as `known objects` (previously announced and announced just before the competition) and `unknown objects`. `Known objects` are divided into two categories: objects that have been previously announced along with the competition rules and objects that will be announced during the `Setup Day`. Each team will bring their own objects for the competition. `Unknown objects` refer to objects that are not on the object list but can be grasped and manipulated. In some competition tasks, these unknown objects may be used during the task.

Finally, the objects used as obstacles are called `dummy objects`, which will be announced on the `Setup Day`.

> [!NOTE]  
> `Known objects` (previously announced): https://github.com/RoboCupAtHomeJP/AtHome2021/blob/master/Data/opl_known_object_list.pdf

### Proportion of the objects

- `Known objects` (previously announced) ｜ Announced: 9 objects　→　During the task: 6 objects
- `Known objects` (during Setup Day) ｜ Announced: 3 objects　→　During the task: 3 objects
- `Unknown objects` (just before the competition) ｜ Announced: 0 objects　→　During the task: 1 object
- `Dummy objects`（during Setup Day）｜ Announced: 3 objects　→　During the task: 3 objects (only one variety)

> [!NOTE]  
> Objects other than `known objects` (previously announced) and `unknown objects` will be provided by the Executive Commitee (EC) to each team on the Setup Day.

> **Warning**
> `Unknown objects` will be changed after all the teams finish the first trial.


## Object Category and Placement Goal

The placement locations for each object category are as follows:
<div align="center"><img src="./tu_layout.jpg" width="70%"></div>
<br>

## Deus ex Machina

The following Deus ex Machina will be adopted in this task. With Deus ex Machina, although no points are awarded for the corresponding action, it is possible to skip partial tasks with simpler methods and continue with the overall task.

<table>
  <tr>
    <th> <b>Action<b> </th>
    <th> <b>Bypassing<b> </th>
  </tr>
  <tr>
    <td> Adjusting the number of objects </td>
    <td>
      <ul>
        <li> Reduce the number of objects to any number </li>
        <li> Allow teams to choose which objects to reduce among the `known objects` </li>
      </ul> 
    </td>
  </tr>
  <tr>
    <td> Object grasping </td>
    <td>
      <ul>
        <li> Referee holds the object instructed by the robot and gives it to the robot (or places it in a specific location) </li>
        <li> At this time, the robot needs to accurately convey the object's position, name, instructions, etc to the referee </li>
      </ul> 
    </td>
  </tr>
   <tr>
    <td> Object placement </td>
    <td>
      <ul>
        <li> Referee places the object that the robot is holding (or is in a specific location) in the location specified by the robot </li>
        <li> At this time, the robot needs to accurately convey the object's placement position, name, instructions, etc to the referee </li>
      </ul> 
    </td>
  </tr>
  <tr>
    <td> Object delivery </td>
    <td>
      <ul>
        <li> The guest receives the object that the robot is holding (or is in a specific location) without being handed over by the robot </li>
        <li> At this time, the robot needs to accurately convey the guest's location, object name, instructions, etc to the referee </li>
      </ul> 
    </td>
  </tr>
</table>


## Score Sheet

<table>
  <tr>
    <th> <b>Action</b> </th>
    <th> <b>Score</b> </th>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>Task 1: Tidy Up Phase</b> </td>
  </tr>
  <tr>
    <td> Tidying up objects <br> 
      <ul>
        <li> Grasping objects (10 points per item) </li>
        <li> Transporting and placing/storing objects (10 points per item) </li>
        <li> Placing/storing objects in the correct location (15 points per item) </li>
      </ul> 
    </td>
    <td align="center"> <!-- 200 <br> --> 10 × 10 <br> 10 × 10 <br> 10 × 15 </td>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>Task 2: Delivery Phase</b> </td>
  </tr>
  <tr>
    <td> Enter `Room 2: Dining Room` without colliding with any obstacle </td>
    <td align="center"> 30 </td>
  </tr>
  <tr>
    <td> Object Delivery <br> 
      <ul>
        <li> Grasping food item from the shelf </li>
        <li> Grasping the instructed food item from the shelf </li>
        <li> Handing over the item to a person </li>
        <li> Handing over the item to the person waving (or raising) its hand </li>
      </ul> 
    </td>
    <td align="center"> <!-- 200 <br> --> 30 <br> 30 <br> 30 <br> 30 </td>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>Penalty</b> </td>
  </tr>
  <tr>
    <td> Non-participation (without previous instance) </td>
    <td align="center"> -500 </td>
  </tr>
  <tr>
    <td> <b>Total (including bonus tasks)</b> </td>
    <td align="center"> <b>500</b> </td>
</table>

**Score Sheet**：[RCJ2023 OPL Tidy Up Score Sheet v1](https://docs.google.com/spreadsheets/d/1Dn0LTINAVYMcSL2Yoqi4iicPZOmU6h8e/edit?usp=sharing&ouid=115914283332872721627&rtpof=true&sd=true)


## Instructions from the Executive Committee (EC)

- Preparation (several days to several weeks before the competition)
  - Selection and purchase of Known objects (during Setup Day) and unknown objects.
- Announcements (30 minutes before the competition)
  - Selection of the placement order of the objects and announce it to the teams.
  - Specify the unknown object and announce it to the teams.


## Role of the Referees (TC)

- Gather 30 minutes before the competition, receive instructions, and receive the score sheet.
- Act as the referee as described during the task.
- Score the competition.
- Verify scoring content with other TCs.
- Submit the score sheet.

> [!NOTE]  
> Members of each teams are selected to be TCs and score the tasks of other teams' competitions. For details, please refer to the [Scoring System](./gr_en.md#scoring-system).
