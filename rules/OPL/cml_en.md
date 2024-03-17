<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./cml_ja.md) | [English](./cml_en.md) 

# Carry My Luggage（CML）

Reference video: https://youtu.be/dzyJ1dHTulc

> [!NOTE]  
> This is a sample video from the previous competition. The rules may differ from the rules in this year.

## Main Goal

In this task, the robot is expected to assist the operator in transporting the luggage to a car parked outside (imaginary). After the robot grabs the luggage (which is a paper bag), it will follow the operator from a known environment to an unknown environment to support the luggage transport. Then, it will autonomously return to the `starting point` (inside the known environment).

**Time Limit**: 7 minutes

## Focus

This task focuses on finger-pointing recognition, manipulation, mapping and navigation in known and unknown environments, human-following, voice dialogue, task planning, etc.

## Settings

- **Location**: An arena environment based on a home environment will be used. The competition will take place both inside and outside the arena. The `inside of the arena` can be mapped in advance (`known environment`), but mapping the `outside` of the arena is prohibited (`unknown environment`).
- **Starting location**: The start location will be announced on the setup day.
- **Luggage (paper bags)**: Two bags will be placed near the operator (within 2\[m\] of the robot and visible to it).
  - **Size**: The bag smaller than in size of 350 x 100 x 350\[mm\] will be used.
  - **Placement**: The possible placement location will be announced on the setup day. A team member places a bag at the location instructed by referee just before the task starts.
- **Operator**: The operator will point to the paper bag to be used during the competition while standing in front of the robot. The operator will be selected from volunteers.

## Scenario

### Starting Phase

1. **Setup**: The referee instructs the team to move the robot to the starting position.
1. **Start**: The referee gives the start signal and starts the timer. At the same time, the team completes the final simple setup (pressing the starting button, etc.) and leaves the area. Complex setup procedures such as pressing more than two buttons are not allowed.
1. **Pointing**: The operator points to the bag that is specified in advance at the same time as the start signal.
1. **Grasping**:  The robot recognizes the bag pointed to by the operator and grasps it.

### Follow-Me Phase

1. **Delivery**: When the robot grasps the bag and becomes ready to follow a person, the robot informs the operator that the robot is ready.
2. **Walking**: The operator starts walking from a known environment towards an unknown environment.
3. **Follow-Me**: The robot follows the operator. When the operator reaches the goal, the operator will inform the robot that the operator has reached the goal. During the follow-me phase, the robot may face up to three obstacles (bonus, the team selects the obstacles to appear in advance.)
   - Small objects on the ground (such as building blocks)
   - Hard-to-see 3D objects (such as chairs or glasses)
   - Opening and closing barriers (such as guide poles)

> [!IMPORTANT]
> (Natural walking) The operator cannot look back to the robot or stop moving when the operator starts walking.

### Navigation Phase

1. **Handover**： The operator receives the bag when the operator and the robot have reached the goal.
2. **Navigation**: The robot autonomously moves from the `unknown environment` to the `Starting Point` in the `known environment`.
3. **Goal**: When the robot returns to the `Starting Point`, the task is complete.
4. **Bonus**: The robot joins at the end of the queue (with 2-4 people) near the goal position.

## Deus ex Machina

The following Deus ex Machina will be adopted in this task. With Deus ex Machina, although no points are awarded for the corresponding action, it is possible to skip partial tasks with simpler methods and continue with the overall task.

|Action|Bypassing|
|------|---------|
| Bag (reduction) | Limit selection to one of the two bags placed (only one bag is placed). |
| Handover | The robot makes the operator to hold the selected bag. At this time, the robot informs the operator of the position of the paper bag. |
| Use markers | Perform following with a marker attached to or held by the operator  |

## Score Sheet

|Action|Score|
|------|-----|
| **Main Task** |  |
| 1. Starting phase | |
| &nbsp;&bull;&nbsp;Detect the selected bag | 50 |
| &nbsp;&bull;&nbsp;Grasp the selected bag | 100 |
| 2. Follow-me phase | |
| &nbsp;&bull;&nbsp;Go out of the arena following the operator | 50 |
| &nbsp;&bull;&nbsp;Arriving at the goal outside the arena | 50 |
| 3. Navigation phase | |
| &nbsp;&bull;&nbsp;Autonomously enter the arena | 25 |
| &nbsp;&bull;&nbsp;Autonomously return to the `starting point` | 25 |
|  |  |
| **Bonus Tasks** |  |
| 2. Follow-me phase | |
| Avoid small objects on the ground (such as blocks) | 50 |
| Avoid visually confusing 3D objects (such as chairs or glasses) | 50 |
| Avoid opening and closing barriers (such as guide posts) | 50 |
| 3. Navigation phase | |
| Join at the end of the queue near the goal | 50 |
| **Penalty** |  |
| Non-participation (without declaration) | -500 |
|  |  |
| Total (including bonus tasks) | 500 |

> [!NOTE]
> Bonus will be scored if one of the main task of the corresponding phase is completed.

## Instructions from the Executive Committee(EC)

- Preparation
  - Select an operator
  - Announce the possible placement locations
  - Select 2-4 people who make a queue near the goal.
  - Select obstacles that the robot will face when it is outside.
- Announcement (Setup day)
  - Select the robot's `starting point` and announce it.
  - Select which bag to be grasped and announce it.
  - Announce the obstacles to be used.
- Announce (just before the competition starts)
  - Select the goal position.
  - Select the position where the bag is placed.

## Role of the Scorer

- Gather 30 minutes before the competition, receive instructions, and receive the score sheet.
- Act as the referee as described during the task.
- Verify scoring content with other TCs.
- Submit the score sheet.

> [!NOTE]  
> Members of each teams are selected to be TCs and score the tasks of other teams' competitions. For details, please refer to the [Scoring System](./gr_en.md#scoring-system).
