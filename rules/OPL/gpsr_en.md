<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./gpsr_ja.md) | [English](./gpsr_en.md)

# General Purpose Service Robot - GPSR

Reference video: https://www.youtube.com/watch?v=Ef1RzF9Wj9U

> [!WARNING]
> This is a sample video for reference and the task content may differ depending on the RoboCup@Home JapanOpen rules.


## Description

Similar to a smart speaker, the robot is asked to execute arbitrary commands requested by an
host.
These commands are classified into four (4) categories according to their complexity.
The score also changes based on the difficulty of the category.


## Focus

*Task planning*, *object/people detection and recognition*, *object feature recognition*, *object manipulation*


## Setup

- **Locations**:
  - **Task location**: The task takes place inside the *Arena*, but some commands may require the robot to go out.
  The *Arena* is in its nominal state for this task.
  - **Start Location**: The robot starts from a *predefined location* announced in the *Setup Days*.
  When the `TC` gives the *start signal*, the robot moves towards the *Instruction Point*.
  - **Instruction Point**: At the beginning of the test, as well as after finishing the first and second command, the robot moves to the *Instruction Point*.
  This *Instruction Point* is announced in the *Setup Days*.
- **People**:
  - **Host**: The host instructs the robot commands given by the `TC`.
  The host is selected from the competing team.
  - **Guests**: Guests interact with the robot through gestures and other means depending on the selected task.
  Up to three (3) guests will be inside the *Arena*.


## Procedure

1. Start Phase

    1. **Task Time**: The time limit is **ten (10) minutes**.

    1. **Setup**: The TC instructs the team to move the robot to the *Start Location*.

    1. **Category Selection**: The team tells the `TC` the selected category.
    Depending on the category, the `TC` choose an arbitrary command and gives it to the host.
        - Category 0: Predefined instructions.
        - Category 1: Low-difficulty instructions.
        - Category 2: Medium-difficulty instructions.
        - Category 3: High-difficulty instructions or instructions containing insufficient/mistaken information.

    1. **Start**: The TC gives the start signal and starts the timer.
    The team completes the setup (pressing the start button, etc.) and leaves the area.
    No complex setup procedures are allowed, such as pressing two or more buttons.

    1. **Goal**: The robot performs the command phase and service phase for three (3) times.

1. Command Phase

    1. **Navigation to Host**: The robot navigates from the *Start Location* to the *Instruction point*.

    1. **Instruct the Robot**: The host commands the given task to the robot.
    If the robot cannot understand the name or favorite drink, the robot can request the guest to repeat the command and no penalty is given.

1. Service Phase

    1. **Command Confirmation**: After receiving the command, the robot confirms it before starting to execute the task.

    1. **Command Execution**: The robot performs the task given in the instructions.


## Additional Rules and Remarks

### Skipping Commands

The robot performs the command phase and service phase for three (3) times.
However, the competing team is able to skip to the next command if the robot misunderstood the given command by the host.
In order to demonstrate so, the robot needs to complete the mistaken task, and go back to the host position requesting for another task.

> [!WARNING]
> Teams may not take advantage of this rule to skip commands until their desired command is given.

### Command Generator

Commands from categories 0-3 are generated using the [CommandGenerator](https://github.com/johaq/CommandGenerator/tree/master).
The TC generates arbitrarily the commands in advance to confirm the commands are correct according to the environment.


## Deus Ex Machina

If the *Deus Ex Machina* listed in the *General Rules* is used during the execution of a task, points are deducted, up to ten (10) times.

For example:
- bypassing speech recognition by using an alternative HRI
- receiving human assistance to accomplish a task
- instructing a human assistant to perform the whole task


## Restart

Restarts are handled as follows, depending on the Phase.
In any case, the robot needs to start from the *Start Point*.
If the robot has completed *Step 1* defined in the [Steps per Category](#steps-per-category) section, the robot can continue the uncompleted task after restarting.
In this case, the robot does not need to repeat *Command Confirmation* from the *Service Phase* as no penalty will be given.
However, the score earned right after the restart is reduced to half as a penalty.

If restart is decided to be done:
- During the understanding of the $n(\le 2)$th command,
  - Resume from the $n$th command.
- During the execution of *Step 1* for the $n$th time
(if not yet arrived at the destination position, the team is not ready to move to the next Step),
  - Resume from the $n$th command.
- After completing *Step 1* for the $n'(\le 3)$th time,
  - Resume from the $n'$th command.

> [!NOTE]
> If the robot is holding an object, the team decides whether to keep it or put it back.


## Command Category

### Task Category Examples

| Category | Example |
| --- | --- |
| **Manipulation** <br>grasp, give\|place | &bullet; Go to the `$ROOM`, grasp the `$OBJECT` on the `$PLACE` and place it on the `$PLACE`. <br>&bullet; Go to the `$ROOM`, grasp the `$OBJECT` on the `$PLACE` and give it to `$PERSON`. |
| **Vision** <br>find (obj \| people)     | &bullet; Tell me how many `$CATEGORY_OBJ` there are on the `$PLACE`. <br>&bullet; Tell me how many people in the `$ROOM` are `$POSTURE`. |
| **Navigation** <br>follow, guide        | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and follow (him \| her). <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and guide `(him\|her)` to the `$ROOM`. |
| **Speech** <br>ask, answer              | &bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and answer (his \| her) question. <br>&bullet; Go to the `$ROOM`, find `$PERSON` at the `$ROOM` and ask (him \| her) `$QUESTION`. |

> [!IMPORTANT]
> Among these four (4) categories, the given command may vary.
Please, refer to the [CommandGenerator](https://github.com/johaq/CommandGenerator/tree/master) for a more detailed sentence structure.

### Steps per Category

| Category | Step 1 | Step 2 | Step 3 | Step 4 |
| --- | --- | --- | --- | --- |
| **Manipulation**    | Move to the object location | Grasp the object                  | Move to the (placement area / person) | (Place / give the object) |
| **Vision**          | Move to the location        | Observe the target                | Move to the host                  | Report the observation result |
| **Navigation**      | Move to the person location | (Follow / guide) the person       | Move to the destination               | (Recognize the end of the following / Report end of the guide) |
| **Speech (ask)**    | Move to the person location | Ask given question to the person  | Move to the host                  | Report the guest's answer to the host |
| **Speech (answer)** | Move to the person location | Request a question to the person  | Answer to the guest's question        | Move to the host |

### Weights per Category

| Category | $Weight$ |
| -------- | ------ |
| 0 | $0.7$ |
| 1 | $1$ |
| 2 | $2$ |
| 3 | $3$ |

## Score Sheet

The robot's actions are divided into four steps, and each step is scored separately.
The variable $Weight$ changes depending on the category difficulty (see the table below).

| Action | Score |
| --- | --- |
|**Main Task**                                            |  |
| &emsp; - Understand the command                         | $3 \times 20$ |
| &emsp; - Execute the 1st command                        | $(5 \times 4) \times Weight$ |
| &emsp; - Execute the 2nd command                        | $(10 \times 4) \times Weight$ |
| &emsp; - Execute the 3rd command                        | $(20 \times 4) \times Weight$ |
| &emsp; - Exit the *Arena* after executing all commands  | $20$ |
| ***Deus Ex Machina***                                                   |  |
| &emsp; - Understand the command using alternative means                 | $3 \times -6$ |
| &emsp; - Execute the 1st command with $h (\le 10)$ times human help(s)  | $-2h \times Weight$ |
| &emsp; - Execute the 2nd command with $h$ times human help(s)           | $-4h \times Weight$ |
| &emsp; - Execute the 3rd command with $h$ times human help(s)           | $-8h \times Weight$ |
| **Penalty**                                             |  |
| &emsp; - Restart                                        | Next earned score  $\times 0.5$| 
| &emsp; - Not attending (absence without permission)     | $-500$ |
| **Total Score**                                         | $500$ |


## Instructions

### To Volunteer

Volunteers are freely selected by the competing team, and will perform the following tasks:

- Select volunteers who will act as `guests`.
- Gather thirty (30) minutes before the test starts.
- Receive instructions about the guests' information.
- The guests may follow the orders given by the robot only,
and not act by their own.

> [!WARNING]
> Any information about the guests must not be shared with the competing team.
Such action may result to the penalty in the scoring or disqualification of the team.

> [!NOTE]
> If the competing team is not able to gather enough volunteers,
support from other teams will be requested.

### To Scorer

Scorers are selected according to the *General Rules* [Scoring System](./gr_en.md#scoring-system) and will perform the following tasks:

- Gather **thirty (30) minutes** before the test starts.
- Receive instructions about the score sheet, guests' information and command.
- Score the competition.
- Confirm the score with the other scorers and TC.
- Submit the score sheet to the TC.

> [!WARNING]
> Any information about the guests must not be shared with the competing team.
Such action may result to the penalty in the scoring or disqualification of the team.

### To TC

- During *Setup Days*:
   - Announce the *Start Location*.
   - Announce the *Instruction Location*.
   - Announce objects, object categories and locations.
   - Announce name and drink list.
- Before the test:
   - Confirm the volunteers (guests/host) selected by the competing team.
   - Assign names and to the volunteers.
   - Confirm the *Command Category* the competing team want to challenge.
   - Arrange the *Arena* based on the commands.
- During the test:
   - Inform the host of the command.
