<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./ri_ja.md) | [English](./ri_en.md)

# Robot Inspection

Reference video: https://youtu.be/JweIZ0n_2gs

> [!NOTE]  
> The reference video is not perfect. The task may differ depending on the rules of each year RoboCup, so please use it as a reference only.
> If you have any concerns or points you would like to discuss, please write them in the [Issues](https://github.com/RoboCupAtHomeJP/Rule2023/issues) section of GitHub.


## Main Goal

This task aims to test the minimum required performance and safety of the robot necessary for the progress of the competition.


## Focus

This task focuses on door opening, navigation, obstacle avoidance, emergency stop, and other skills.


## Settings

- **Location**: An arena environment based on a home environment will be used. The competition will take place both inside and outside the arena.
- **Start Location**: The robot will start from outside the arena.
- **End Location**: The robot will move towards the middle point of the `Room2: Dining Room`.


## Scenario

### Starting Phase

1. **Number of Trials**: There is no limit to the number of trials for this task. As long as the time allows it, the team can attempt the task as many times as necessary to achieve a perfect score.
1. **Competition Time**: The competition time for each trial is **5 minutes**.
1. **Setup**: The referee instructs the team to move the robot to the starting position.
1. **Start**: The referee gives the start signal and starts the timer. At the same time, the team completes the final simple setup (such as pressing the start button) and leaves the area. It is not allowed to perform complex setup procedures such as pressing two or more buttons. In addition, the team will be disqualified immediately if they touch the robot after this point.
1. **Door Opening**: At the start signal, one person from the team opens the door. The robot recognizes that the door has opened and autonomously enters the arena.

### Navigation Phase

1. **Navigation**: The robot moves towards the exit of the arena. During this time, the robot is subjected to interference from TCs. The robot detects the TC and avoids the collision safely, or stops in place until the TC press the emergency button.
1. **Goal**: If the TC presses the emergency stop button provided on the robot and the robot stops safely and quickly in place, the task ends.

> **Warning**
> The emergency stop button is a mandatory requirement for the robot. Robots without this button will be disqualified.

> **Warning**
> In the case of multiple robots, all robots participating in the competition must participate in the `Robot Inspection`.
> In addition, if sensors or actuators installed on the robot are changed for each competition, all versions used in the competition must participate in the `Robot Inspection`.
> Only the highest score from all trials with all robots and all its versions will be selected and adopted as the team's score.


## Deus ex Machina

The following Deus ex Machina will be adopted in this task. With Deus ex Machina, although no points are awarded for the corresponding action, it is possible to skip partial tasks with simpler methods and continue with the overall task.

<table>
  <tr>
    <th> <b>Action<b> </th>
    <th> <b>Bypassing<b> </th>
  </tr>
  <tr>
    <td> Door Open </td>
    <td>
      <ul>
        <li> Enter the arena without detecting door opening </li>
        <li> However, you will need to prepare a different startup method, such as "touching the arm" or "pressing a button", and convey that startup method to the TC. </li>
      </ul> 
    </td>
  </tr>
   <tr>
    <td> Obstacle Avoidance </td>
    <td>
      <ul>
        <li> Eliminate obstacles to progress caused by people </li>
      </ul> 
    </td>
  </tr>
</table>

   
## Score Sheet

In this task, only the highest score will be recorded as the score.

<table>
  <tr>
    <th> <b>Action</b> </th>
    <th> <b>Score</b> </th>
  </tr>
  <tr>
    <td colspan="2" align="center"> <b>Main task</b> </td>
  </tr>
  <tr>
    <td> Detect door opening and enter the arena </td>
    <td align="center"> 20 </td>
  </tr>
  <tr>
    <td> Start moving autonomously towards the exit of the arena </td>
    <td align="center"> 20 </td>
  </tr>
  <tr>
    <td> Avoid the colission with the TC and stop in place </td>
    <td align="center"> 30 </td>
  </tr>
  <tr>
    <td> When the emergency stop button is pressed, stop safely and quickly </td>
    <td align="center"> 30 </td>
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
    <td align="center"> <b>100</b> </td>
  </tr>
</table>


## Instructions from the Executive Committee (EC)

- Announcement (2 hours before the competition)
  - Announce the entrance to the arena
  - Announce the exit of the arena
- Just before the competition starts
  - Close the door at the entrance to the arena
  - Confirm with the team whether they will skip any sub-tasks
