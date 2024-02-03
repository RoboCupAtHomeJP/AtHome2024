<sub>[Go back to README](../../README_en.md)</sub>

[日本語](./gr_ja.md) | [English](./gr_en.md)

# General Rules & Regulations

The competition in the Open Platform League (`OPL`) of RoboCup Japan Open @Home 2023 (referred to as "RCJ2023" below) will be held in accordance with the General Rules & Regulations described on this page. These General Rules & Regulations have been created based on Chapter 3 `General Rules & Regulations` of the [RoboCup 2022 Rulebook (Rev-1298)](https://athome.robocup.org/wp-content/uploads/2022_rulebook.pdf).

Regarding any changes not mentioned on this page related to the [RoboCup 2022 Rulebook (Rev-1298)](https://athome.robocup.org/wp-content/uploads/2022_rulebook.pdf) will not be considered. Therefore, the rules will be finalized through discussions with participating teams via GitHub Issues.

> **Warning**
> If there is any inconsistency between the Japanese version and English version of the RCJ2023 General Rules & Regulations, we will take the Japanese version as priority.


## Team Registration and Qualification

Team Registration will be conducted through the Japan RoboCup Committee. There are two stages of registration for RCJ2023.

1. Pre-registration
1. ~~Qualification process~~
1. Final registration

Information on pre-registration and final registration will be announced on the RoboCup@Home JP mailing list and Slack. No qualification process will be conducted. All teams that have completed registration can participate.

### Pre-registration

Please register for RCJ2023 using the following link. The deadline for team registration is `Friday, March 31, 1:00 PM`. We look forward to your registration.

> [!NOTE]  
> Pre-registration form: https://forms.gle/wzCGnJwkGiw2KUfg8

Please note that the following leagues will be held. If your team plans to participate in multiple leagues, please fill out separate registration forms for each league.

- Open Platform League（OPL）
- Domestic Standard Platform League（DSPL）
- Education League
- Simulation Open Platform League（S-OPL）

> [!NOTE]  
> All leagues will be held on-site only. Please be aware of this.

### Final Registration

Final registration for RCJ2023 will be conducted using the "Participation Registration" (Google Form) on the website below. For more details, please refer to the [Registration Procedure]((https://www.robocup.or.jp/japanopen2023/english.html)) on the official website.

Please use the team code issued at the time of pre-registration.

> [!NOTE]  
> Final Registration Form：https://docs.google.com/forms/d/e/1FAIpQLSeYN8dRqkmi4Q_4idUBG4yEoLghzEcGQVQHaSru67Fn1A4CtQ/viewform


## Organization

### Executive Committee - EC

The Executive Committee (EC) is responsible for the rules of the league and the progress of the competition. The EC is composed of one member from the previous year's winning team and one member from the runner-up team. Their main responsibilities include the management of the competition, the creation of the rulebook, and refereeing. At RoboCup Japan Open @Home, EC members also serve as TC members.

### Technical Committee - TC

The technical committee (TC) is responsible for the rules of the league; its main focus is writing the rulebook and refereeing. The members of the EC are always members of the TC as well.

### Organizing Committee - OC

The organizing committee (OC) is responsible for the organization of the competition, namely it creates the schedule and provides information about the scenarios. The Local Organizing Committee (LOC), on the other hand, is responsible for the set up and organization of the competition venue.


## Audience interaction

Part of making RoboCup@Home appealing is to show the audience what robots should do and what they are actually doing during tasks. In particular, providing information about what a robot is doing to the audience is important for the advancement of the league．Therefore, competition scenes may be distributed using video distribution services such as YouTube. As event organizers, we take care to ensure that the audience does not disturb the robot's actions as much as possible. However, it is necessary for each team to consider measures to deal with situations where tasks performed inside the arena are not affected for example in the recognition system of the robot because of the movements of spectators outside the arena (e.g., issues with human pose estimation).


## Scenario

Most competition tests take place in the RoboCup@HomeArena, but some tests may take place outside, in a previously unknown public place. In this section, the [Arena](#arena) and its contents are described, in particular the furnishing and other information that is common between tests and leagues.

### Arena

The `RCJ2023` Arena is based on the `WRS2020` competition arena environment．
<!-- RoboCup@Homeでは，それぞれの場所には，場所クラスが設定されています． -->

However, as robots need to function in the real world, the arena is not fixed and may be changed without notice.

1. **Major changes**: Any furniture (at a Predefined Location or not) that cannot be expected to be fully static in an everyday environment might be moved slightly between tests. In particular, furniture will not change rooms or move drastically inside a room, but a couch or table may be slightly rotated or moved; fixed locations for such furniture items should not be assumed. Walls will stay in place and rooms will not change function. Passages might be blocked.

1. **Minor changes**: Slightly moved chairs, slightly closed doors, or anything similar cannot be avoided and might happen at any time, even during a test.

### Objects

We have prepared a list of 9 objects to be used in tasks based on RCAP2021. The object list can be found at the link below. The list includes photos, official names, and object categories (for example, `Noodle` belongs to the `Food` category). Most objects are lightweight and easy for the robot to grasp. For each object category, the location where it should be placed and the place where it should be tidied up are predetermined. By referring to this category, the team will find and tidy up objects during the competition. Please note that modification of the objects is prohibited.

In addition, in the competition tasks, objects used are `known objects` (previously released + released just before the competition) and `unknown objects`. `Known objects` are divided into two types: objects that have been released in advance at the same time the rules were published and objects that will be released in the `Setup Day` of the competition. For the main competition, each team will use the objects they have brought. `Unknown objects` refer to objects that are not on the object list but can be grasped and operated. Depending on the competition task, these unknown objects may be used.

> [!NOTE]  
> Previously released list of known objects (used on the RCAP2021): https://github.com/RoboCupAtHomeJP/AtHome2021/blob/master/Data/opl_known_object_list.pdf

### Predefined Person Names

Some tests in the RoboCup@Home league involve memorizing a person’s name. All people in the Arena have an assigned Predefined Name chosen by the TC.

### Wireless network

In `RCJ2023`, a wireless communication network environment will not be provided. Please be aware of that.

<!--
Therefore, the use of team-specific WiFi access points will be allowed at the venue.

> **Warning**
> If any unnatural robot movements (caused by remote operation or other means) are detected, penalties such as deduction of points, disqualification, or even disqualification of the entire competition may be imposed.
-->

## Robots
`The robots used in RCJ2023 must meet the following requirements. Verification of compliance will be conducted at the [Robot Inspection](./ri_en.md).

### Number of Robots

1. **Number of registered robots**: Each team can register up to two robots, but only robots that have cleared the [Robot Inspection](./ri_en.md) can be used in the competition.

1. **Number of robots during competition tasks**: Only one robot can be used in each competition test. Different robots can be used in different competition tests.

1. **Number of robots in the Technical Challenge**: In the Technical Challenge, teams can use a maximum of two registered robots simultaneously.

### Robot Specification
Robots participating in the RoboCup@Home Open Platform League must comply with the following specifications to ensure that they do not cause harm during operation.

#### **Size and Weight**

1. **Dimensions**: The dimensions of a robot should be able to pass through the door used in the task environment (1.2 [m]). The TC may allow the qualification and registration of larger robots, but, due to local restrictions, it cannot be guaranteed that the robots can actually enter the Arena. In doubt, please contact the organizers.

1. **Weight**: There are no specific weight restrictions; however, the weight of the robot and the pressure it exerts on the floor should not exceed local regulations for the construction of offices and/or buildings which are used for living in the country where the competitions is being held.

1. **Transportation**: Team members are responsible for quickly moving the robot out of the
Arena. If the robot cannot move by itself (for any reason), the team members must be
able to transport the robot away quickly and easily.

#### **Appearance and Safety**

1. **Cover**: The robot’s internal hardware (electronics and cables) should be covered so that safety is ensured. The use of (visible) duct tape is strictly prohibited.

1. **Loose cables**: Loose cables hanging out of the robot are not permitted.

1. **Safety**: The robot must not have sharp edges or elements that might harm people.

1. **Annoyance**: The robot must not be continuously making loud noises or use blinding lights.

1. **Driving**: To be safe, the robots should be careful when driving. Obstacle avoidance is mandatory.

<!-- 1. **Marks**: The robot may not exhibit any kind of artificial marks or patterns. -->
<!-- ロゴとかをつけているチームやハンドにQRマーカをつけているチームがある． -->

#### **Emergency Stop Button**

1. **Accessibility and visibility**: Every robot has to provide an easily accessible and visible Emergency Stop button.

1. **Color**: The Emergency Stop must be coloured red and be the only red button on the robot. The TC may ask the team to tape over or remove any other red buttons present on the robot.

1. **Robot behavior**: When the Emergency Stop button is pressed, the robot and all its
parts must stop moving immediately.

<!-- スタートボタンについては要検討 -->

<!-- 外部機器については要検討 -->
<!-- ## 5 外部機器
チームが競技中に使用するロボットの一部でないものは全て「外部機器」とみなされます．全ての外部機器は，[Robot Inspection](https://github.com/RoboCupAtHomeJP/Rule2023/blob/rules/opl/robot_inspection.md)において，運営の認可を受けなければいけません．この際，運営は外部機器を自由に使用できるか，審判の監視下で使用できるかを指定し，採点に与える影響を判断します．なお，イヤホンやヘッドホンなどの無線機器の使用は，外部機器としても使用が認められません．また，大会主催者は，アリーナ内のネットワークやインターネット接続の可用性や信頼性に関して，いかなる保証や責任も負わないことに注意してください．チームは自己の責任において外部機器を使用することができます．
-->


## Organization of the Competition

The RCJ2023 competition will be held over several days with tasks that will be published in the [AtHome2023](https://github.com/RoboCupAtHomeJP/AtHome2023).

### Scoring System

The RCJ2023 competition includes two events: the `competition tasks` and the `Technical Challenge`, which is a research presentation. The scoring for each event will be separate and will have separate awards. Participants can choose to compete in one or both events, and should inform the organizers of their participation in advance.

#### **Tasks**

All teams have the right to participate in all the competition tasks at RCJ2023. These tasks will be carried out according to separate announcements regarding the rules, point system, and schedule. Teams will compete based on the total highest score obtained in each task, except for the `Technical Challenge`. The maximum score for each task, except for `Robot Inspection`, is 500 points. The scoring process is as follows:

Scoring will be carried out by two members of each team, one from their own team and one from another team, in a clockwise order. For example:

- First Task
  - `Team A` scoring: 1 member from `Team A` and 1 member from `Team B` (2 members total)
  - `Team B` scoring: 1 member from `Team B` and 1 member from `Team C` (2 members total)
  - `Team C` scoring: 1 member from `Team C` and 1 member from `Team A` (2 members total)
- Second Task
  - `Team A` scoring: 1 member from `Team A` and 1 member from `Team C` (2 members total)
  - `Team B` scoring: 1 member from `Team B` and 1 member from `Team A` (2 members total)
  - `Team C` scoring: 1 member from `Team C` and 1 member from `Team B` (2 members total)
- And so on

> [!NOTE]  
> The RCJ2023 OPL aims to have a strong connection with the Education League. It is hoped that the technical skills acquired in the Education League will be demonstrated in the OPL. To this end, the `Carry My Luggage` competition from the Education League will be adopted in the OPL, and the rules for this competition will be the same as those for the Education League.

#### **Technical Challenge**

All teams have the right to participate in the `Technical Challenge` at `RCJ2023`. This event will be carried out according to separate announcements regarding the rules, point system, and schedule. This is an opportunity to showcase unique technical skills, and teams will be judged based on their presentations and demonstrations by a panel of judges.

### Schedule

Details of the schedule for the competition will be publish in the [AtHome2023](https://github.com/RoboCupAtHomeJP/AtHome2023) repository.

## Procedure during Tests

The competition of `RCJ2023` will be carried out following a predetermined procedure. Please, pay attention to the following points.

### Safety First!

1. **Emergency Stop**: At any time when operating the robot inside and outside the scenario the owners have to stop the robot immediately if there is a possibility of dangerous behavior towards people and/or objects.

1. **Stopping on request**: If a referee, member of the Technical or Organizational committee, an Executive or Trustee of the federation stops the robot (by pressing the emergency button) there will be no discussion. Similarly if they tell the team to stop the robot, the robot must be stopped immediately.

1. **Penalties**: If the team does not comply, the team and its members will be excluded from the ongoing competition immediately by a decision of the RoboCup@Home Technical Committee (TC). Furthermore, the team and its members may be banned from future competitions for a period not less than a year by a decision of the RoboCup Federation Trustee Board.

### Maximum number of team members

1. **Regular Tasks**: During a regular task, the maximum number of team members allowed inside the Arena is one (1). Exceptions are tasks that explicitly require volunteer assistance.

1. **Setup**: During the setup of a task, the number of team members inside the Arena is not limited.

1. **Technical Challenge**: During the `Technical Challenge`, the number of team members inside the Arena is not limited.

### Fair Play

Fair Play and cooperative behavior is expected from all teams during the entire competition, in particular:
- while evaluating other teams,
- while refereeing, and
- when having to interact with other teams’ robots.

This also includes:
- not trying to cheat (e.g., pretending autonomous behavior where there is none),
- not trying to exploit the rules (e.g., not trying to solve the task but trying to score), and
- not trying to make other robots fail on purpose.
- not modifying robots in standard platforms.


> **Warning**
> Disregard of this rule can lead to penalties in the form of negative scores, disqualification for a test, or even for the entire competition.

### Expected Robot’s Behavior

Unless stated otherwise, it is expected that the robot always behave and react in the same way a polite and friendly human being would do. This applies also to how robots try solve the assigned task As rule of thumb, one may ask any non-scientist how she would solve the task.
Please consider that average users will not know the specific procedure to operate a robot. Hence, interaction should be as with any other human being.In detail, we require your robot to speak out what it is about to do.

### Robot Autonomy and Remote Control

1. **No touching**: During a test, the participants are not allowed to make contact with the robot(s), unless it is in a “natural” way and required by the task.

1. **Natural interaction**: The only allowed means to interact with the robot(s) are gestures and speech.

1. **Natural commands**: Anything that resembles direct control is forbidden.

1. **Remote Control**: Disregard of these rules will lead to disqualification for a test or for the entire competition.

> **Warning**
> Disregard of this rule can lead to penalties in the form of negative scores, disqualification for a test, or even for the entire competition.

### Collisions

1. **Touching**: Gently touching objects is tolerated but unadvised. However, robots are not
allowed to crash with something. The 「[safety first!](#safety-first)」 rule overrides any other rule.

1. **Major collisions**: If a robot crushes into something during a test, the robot is immediately stopped. Additional penalties may apply.

1. **Functional touching**: Robots are allowed to apply pressure on objects, push away furniture and, in general, interact with the environment using structural parts other than their manipulators. This is known as functional touching. However, the robot must clearly announce the collision-like interaction and kindly request not being stopped.

1. **Collision avoidance between robots**: If two robots encounter each other in a competition, both robots must actively try to avoid the other robot. Robots that do not aim for a different route within a reasonable time (e.g. 30 seconds) may be removed.

> **Warning**
> Referees can (and will) immediately stop a robot in case or suspicion of dangerous behavior.

### Removal of robots

Robots not obeying the rules are stopped and removed from the Arena.

1. It is the decision of the referees and the TC member monitoring the test if and when to remove a robot.

1. When told to do so by the referees or the TC member monitoring the test, the team must immediately stop the robot, and remove it from the Arena without disturbing the ongoing test.

### Start signal

The default start signal (unless stated otherwise) is door opening. Other start signals are allowed but must be authorized by the Technical Committee (TC).

### Entering and leaving the Arena

1. **Start position**: Unless stated otherwise, the robot starts outside of the Arena.

1. **Entering**: The robot must autonomously enter the Arena right after the door is opened.

> [!NOTE]  
> After the robot enters through the `door open`, it is possible to close the door that was used. In this case, if the robot is not blocking the passage, it is considered as entered.

### Operators

In RCJ2023, operators of robots are generally allowed to be from the same team. However, in some cases, operators other than the same team may be selected by the organizers.

### Time limits

In RCJ2023, the time limits set for each task are strictly followed, and there are no additional points for completing a task quickly.

### Restart

In RCJ2023, teams are allowed to restart as many times as they want within the time limit. However, the points earned right after the restart will be reduced to half.

If the robot is holding an object during a restart, the team can choose whether to keep it or release it. Objects released will be stored outside the arena and cannot be used again until the end of the task.

### Verification in Voice Recognition

In `RCJ2023`, there is no deduction based on the number of times a team uses voice recognition to verify a task. However, there are time limits for each task, so it is recommended to use strategies such as [Deus Ex Machina](#deus-ex-machina-bypassing-features-with-human-help) to operate the robot and score points as much as possible.

### Placement of the objects

In `RCJ2023`, teams are allowed to place the objects to be used in the competition. However, the order and use of the objects specified by the organizers must be followed during the competition.


## Deus ex Machina: Bypassing Features With Human Help

Robots can’t score unless they accomplish the main goal of a task. However, in many real-life situations, a minor malfunction may prevent the robot from accomplishing a task. To prevent this situation, while fostering awareness and human-robot interaction, robots are allowed to request human assistance during a task.

To avoid undesirable situations for both teams and spectators, such as tasks not starting due to voice recognition not working, or tasks not continuing because objects cannot be grasped, it is recommended to actively use means to avoid those partial tasks.

### Usage

The procedure to request human assistance while solving a task is as follows:

1. **Request help**: The robot must indicate loud and clear that it requires human assistance.

It must be clearly stated:
    - The nature of the assistance
    - The particular goal or desired result
    - How the action must be carried out (when necessary)
    - Details about how to interact with the robot (when necessary)

1. **Supervise**: The robot must be aware of the human’s actions, being able to tell when the requested action has been completed, as well as guiding the human assistant (if necessary) during the process.

1. **Acknowledge**: The robot must politely thank the human for the assistance provided.

### Examples

For each competition task, `Deus Ex Machina` provides various items. For details, please check each task contents. If you want to add any additional `Deus Ex Machina` rule, please let us know on GitHub Issue. We would like to actively consider and adopt them.

<!--
`RCJ2023` strongly recommends the following Deus Ex Machina in particular:

- Ensure reliable alternative means of voice recognition through active use of QR codes.
- Utilize interaction methods such as touch displays mounted on robots.
- Provide instructions to referees using the robot's voice and display.
-->

Referees will respond as much as possible to clear instructions given by the robot, such as "Open the door," "Move the chair," or "Take the object and put it in the hand." However, they cannot handle points that exceed the limits of the referee, such as unclear voice, instructions in languages other than English or Japanese, or images that are too small to read.

> **Warning**
> Directly sending commands to the robot is prohibited even in `Deus Ex Machina`. The main purpose of this tool is to simplify interactions with the robot.

### Scoring System

There is no limit on the number of times a robot can use a `Deus Ex Machina` that requires assistance from a human. However, using `Deus Ex Machina` may result in a deduction or loss of points for the task. For details, please refer to the rules for each competition task.


## Penalty for not attending

In addition to penalties during the competition, penalties will also be imposed for unauthorized absence. Please check the following points until the start of the competition.

1. **Automatic schedule**：All teams are automatically scheduled for all tests. However, if you inform the organizers your intention of not participating in a specific task when registering, your team will be excluded from the schedule for the requested task.

1. **Announcement**: If a team cannot participate in a test (for any reason), the team leader has to announce this to the OC at least 60 minutes before the test slot begins.

1. **Penalties**: A team that is not present at the start position when their scheduled test starts, the team is not allowed to participate in the test anymore. If the team has not announced that it is not going to participate, it gets a penalty of 500 points.
