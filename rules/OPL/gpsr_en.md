<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./gpsr_ja.md) | [English](./gpsr_en.md)

# General Purpose Service Robot (GPSR)

参考動画：https://youtu.be/p9ki89buY68 <br>
> [!NOTE]  
> この動画は参考動画である．RoboCupのルールによってタスク内容が異なる可能性がある．
> 質問や議論は，GitHubの[Issues](https://github.com/RoboCupAtHomeJP/Rule2023/issues)にて行う．

> [!NOTE]  
> このルールはRoboCup JapanOpen2022 OPLのGPSRに基づき作成されたものである．

## Main Goal

The robot responds to various requests from the user. No predetermined task flow, commands, or action content is defined. Tasks requested by the user in the competition are randomly selected by the TC from a large number of tasks prepared. These commands are classified into four categories according to their complexity, and the score changes based on the difficulty of the category.

## Focus

Complex spoken dialogues, execution of undefined instructions, efficient and speedy task execution, mapping and navigation in known environments, task planning

## Setup

- **Location**: The place where the task is performed is announced in advance.
- **Start Location**: The robot starts from the predefined location announced in advance.
- **Operator**: The operator instructs the robot to perform randomly selected tasks. The operator is selected from each team member.
- **Guest**: Guests interact with the robot through gestures and other means depending on the selected task. Up to three guests will be selected, and they are selected from each team member.

## Scenario

### a. Start phase

1. **Time limits**: The competition time is 10 minutes.
2. **Setup**: The TC instructs the team to move their robot to the starting position.
3. **Start**: The TC signals the start and starts the timer. The team completes the final simple setup, such as pressing the start button, and leaves the area. Complex setup steps such as pressing more than two buttons are not allowed.
4. **Goal**: For one command task, the robot performs the command phase and service phase three times.

### b. Command phase

1. **Category Selection**: The team tells the referee the desired category. Depending on the selected category, the referee gives the task command to the operator.
   - Category 1: Low-difficulty instructions.
   - Category 2: Medium-difficulty instructions.
   - Category 3: High-difficulty instructions or instructions containing insufficient/mistaken information.
2. **Commands to Robot**: The operator commands the selected task to the robot. If the robot does not understand the operator's command, the operator can repeat the command.

## c. Service phase

1. Repetition of instructions: After receiving instructions, the robot repeats them before starting to act.
2. Service: The robot executes the task given in the instructions. After completing the task, it returns to the operator for the next set of instructions. It is unnecessary to open the door again and enter the arena.

## Remarks

### Prohibition of skipping

The task is comprised of three steps, with the score increasing for each step. The scoring step is advanced if at least step 1 of the current command is completed.

### Command generator

Commands from categories 1-3 are generated using the [command generator](https://github.com/kyordhel/GPSRCmdGen/tree/legacy). The TC generates enough commands in advance and changes the variables of the commands according to the test environment as needed. The commands used in the task are selected at random from the generated commands.

## Deus ex Machina

If the deus ex machina listed in the General rules is used, the score for the task will be deducted as shown in the score sheet. If Deus ex Machina is used during the execution of a task, points are deducted for the number of times (up to 10 times) that Deus ex Machina is used, regardless of the type of Deus ex Machina (examples include grasping and placement by a human, and speech recognition by alternative means). Refer to each task in the RoboCup 2022 Rulebook for the specific example of Deus ex Machina.

## Restart

Restarts are handled as follows, depending on the stage. If the robot has completed Step 1, the robot can continue the previous task after restarting. In this case, the robot may repeat command understanding and task execution, and once scored, no points will be deducted. However, the score earned right after the restart is reduced to half as a penalty.

- While understanding the $n(\le 2)$th command,
  - Resume the next command as the $n$th command.
- While the execution of Step 1 for the $n$th time (not yet arrived at the destination position; not ready to move to the next Step),
  - Resume the next command as the $n$th command.
- After completing Step 1 for the $n'(\le 3)$th time,
  - Can resume the $n'$th command. If the robot holding an object, the team decides its handling.

## コマンドセット

| Task category | Example commands |
| --- | --- |
| **Carrying** | &bullet; Go to the ` $ROOM`, grasp the `$OBJECT` on the `$PLACE` and place it on the `$PLACE`. <br>&bullet; Go to the `$ROOM`, grasp the `$OBJECT` on the `$PLACE` and give it to `$PERSON`. |
| **Vision** <br>find (obj \| people) | &bullet; Tell me how many `$CATEGORY_OBJ` there are on the `$PLACE`. <br>&bullet; Tell me how many people in the `$ROOM` are `$POSTURE`. |
| **Navigation** <br>follow, guide | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and follow (him \| her). <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and guide `(him\|her)` to the `$ROOM`. |
| **Speech** <br>question, answer | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and answer (his \| her) question. <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and ask (him \| her) `$QUESTION`. |

## Score Sheet

The robot's actions are divided into four steps, and each step is scored separately. The variable $cat$ changes depending on the category difficulty (see the table below).

| Action | Score |
| -- | -- |
|**Main Task** |  |
| Understand the command | $3 \times 20$ |
| Execute the 1st command | $(5 \times 4) \times cat$ |
| Execute the 2nd command | $(10 \times 4) \times cat$ |
| Execute the 3rd command | $(20 \times 4) \times cat$ |
| Exit the arena after executing all commands | $20$ |
| **Deus Ex Machina** |  |
| Understand the command using alternative means | $3 \times -6$ |
| Execute the 1st command with $h (\le 10)$ times human help(s) | $-2h \times cat$ |
| Execute the 2nd command with $h$ times human help(s) | $-4h \times cat$ |
| Execute the 3rd command with $h$ times human help(s) | $-8h \times cat$ |
| **Penalty** | |
| Restart | Score earned right after the restart  $\times -0.5$| 
| Not attending (absence without permission) | $-500$ |
| **Total** | $500$ |

### Steps per Task Category

| Tasks | Step 1 | Step 2 | Step 3 | Step 4 |
| --- | --- | --- | --- | --- |
| **Carrying** | Move to the object | Grasp the object | Move to the (placement area / person) | (Place / give the object) |
| **Vision** | Move to the (room / place) to observe | Observe the target | Move to the operator | Report the observation result |
| **Navigation** | Move to the person | (Follow / guide) the person | Move to the destination | (Recognize the end of the following / Report the end of the guide) |
| **Speech(ask)** | Move to the person | Ask question to the person | Move to the operator | Report the answer of the question |
| **Speech(answer)** | Move to the person | Request for the question | Answer the question | Move to the operator |

### Weights per Category

| Category | $cat.$ |
| -------- | ------ |
| 0 | $0.7$ |
| 1 | $1$ |
| 2 | $2$ |
| 3 | $3$ |

## Instructions for TC

- Preparation
  - Assign names to two volunteers.
  - Inform the operator of the command.
- Announcement (Setup day)
  - Publish room, location, and personnel names.
  - Publish predefined object locations.
  - Publish predefined instruction locations.
  - Publish the location of the entrance and exit doors of the arena.

## Referee's Movement

Referees selected according to the General Rules will perform the following.

- 30 minutes before the start of the competition, receive instructions, a score sheet and a command list.
- Act as the referee described in the scenario.
- Score the competition.
- Verify the score with other referees and TC.
- Submit the score sheet to TC.
