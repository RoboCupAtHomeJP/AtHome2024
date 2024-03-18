[日本語](./make_task_ja.md) | [English](./make_task_en.md)

# Competition Task Creation Procedure

For fairness, each team is required to create a part of the problems used in the competition.
You can check the problem creation procedure for each competition from the following:

For Handyman and Interactive Cleanup, the method of creating tasks is also explained in the video, which can be checked here.

[Task Creation Procedure Video](https://youtu.be/JrrpMxX3Vh8)

## Spreadsheets
The creation of competition tasks will proceed by adding task content sheets to a Google Spreadsheet.
- [Handyman Task Description Template](https://docs.google.com/spreadsheets/d/1mMqzx-0CZG0YOU-FLNQnZLh0BB7g3noFKtWkBDInizA/edit?usp=sharing)
- [InteractiveCleanup Task Description Template](https://docs.google.com/spreadsheets/d/1-ZKrXuRVkZL1UqjX_ld2nFJ09bWUW1WfOwaq7lt5qFg/edit?usp=sharing)
- [HumanNavigation Task Description Template](https://docs.google.com/spreadsheets/d/1SK99wUuujxUdwD_PsWOkBpM4jD_pY_QRzsUibcTXRNU/edit?usp=sharing)

# Creating Handyman Competition Tasks

For the basic flow of task creation, please refer to GitHub's [Readme](https://github.com/RoboCupatHomeSim/handyman-unity) and [Wiki](https://github.com/RoboCupatHomeSim/handyman-unity/wiki/AdvancedExecutionProcedures#how-to-create-the-environmentinfoxxjson). Confirm whether the layout created is appropriate by following the steps below.

## About Difficulty Adjustment
- The difficulty level of the tasks should primarily be easy.
- Ensure sufficient differences in difficulty between trials. Currently, many tasks are easy, so this is not a problem.
- Elements that affect difficulty:
  - Room size
  - Narrowness of passageways
  - Presence of dynamic obstacle avatars (EthanWoman)
  - Length of the movement distance
  - Layouts with many objects
  - If the grasping target is an a-like object
  - Movement of the instructor (Ethan)
  - If the destination for the grasping object is movable furniture (such as a trash can)
  - If the task message includes words expressing spatial relationships
  - If the task message contains contradictions
  - If the grasping target is lying down
- Currently, unknown environments are not set, and everything is published in advance.

## Task Creation Steps

1. **Google Spreadsheet Preparation**:
   - Proceed by adding task content sheets to a Google Spreadsheet named "HandymanTask Template."

   [Template Here](#Spreadsheets)

2. **Copy Template Sheet**:
   - Copy the template sheet to create a task sheet. The template sheet varies for each layout.

3. **Devising Tasks**:
   - Think and revise a task sentence that uniquely determines the grasping target and the delivery destination. Keep the task sentence to about 150 characters.

4. **Creating Tasks in Unity**:
   - Copy the competition scene (Handyman.unity) in Unity and create a scene for task creation. Place the scene for task creation in the `Assets/AssetStoreTools` folder and prevent it from being accidentally pushed to GitHub using gitignore settings.

5. **Detailed Task Adjustment**:
   - Following the Wiki procedure, adjust the GraspingCandidatesPositionXX and move the trash can if necessary.

6. **Saving Files**:
   - The task is output to AvatarMotions01.dat and EnvironmentInfo01.json, so copy and save these files.

7. **Task Confirmation**:
   - Set isGraspableObjectsPositionRandom back to false, use the competition scene to run the created task, and confirm that the task is as expected.

## Task Operation Confirmation

1. **Preparation of Unity Scene for Official Use**:
   - Copy Handyman.unity and create a Unity scene for official use under the Hidden folder.

2. **Adding a-like Objects**:
   - Add a-like objects under GraspingCandidates of the official Unity scene.

3. **Confirming the Operation of All Tasks**:
   - Use the official Unity scene to check the operation of all created tasks.

## Updating the 3D Model List (Object Label List)

- The list of 3D models used in each competition is shared in advance with participants via a Google Spreadsheet named Object Label.
- Updates include adding new 3D models or changing the handling of existing 3D models.


<br>
<br>

# Interactive Cleanup Task Creation Procedure

For the basic flow of task creation, please refer to GitHub's [Readme](https://github.com/RoboCupatHomeSim/interactive-cleanup-unity) and [Wiki](https://github.com/RoboCupatHomeSim/interactive-cleanup-unity/wiki/AdvancedExecutionProcedures#generate-the-competition-data-using-oculus-quest-2). Confirm whether the layout created is appropriate by following the steps below.

## About Difficulty Adjustment

Before creating tasks, please go through the items related to task difficulty adjustment.

- Currently, the difficulty should be set to easy.
- Difficulty is primarily controlled by pointing gestures.
- Ensure sufficient differences in difficulty between trials.
  - Currently, the difficulty of all tasks is set to easy.
- The more the avatar moves, the higher the difficulty.
  - Currently, all movement distances are short.
- The faster the avatar's movement speed, the higher the difficulty.
  - Currently, the movement speed is fixed at default (slow).
- Do not place more than one graspable object on desks or shelves. Do not place two objects on one desk.
- Many objects are placed on the floor by default, but as obstacle objects increase the difficulty, move them to positions where they will not interfere if not intentional.
- The shorter the pointing time, the higher the difficulty.
  - The pointing time should be about 6 seconds to 10 seconds. For example, if it's 10 seconds, send the pointing order after maintaining the pointing shape for 5 seconds, then continue to maintain the pointing shape for another 5 seconds.
- The further the pointing target, the higher the difficulty.
- Pointing with the back turned to the robot increases the difficulty.
  - Due to the high difficulty, do not create tasks with extreme back-turning pointing at this time.
- Bending the elbow during pointing increases the difficulty.
  - Currently, the arm should be extended as straight as possible.

### Note

- Most of the graspable objects placed on the floor are at a height that cannot be detected by the laser range finder.

## Task Creation Steps

Proceed by creating task files while adding task content sheets to a Google Spreadsheet named "InteractiveCleanupTask Template." Open the InteractiveCleanupTask Template while working.

[Template Here](#Spreadsheets)

1. Copy the "template" sheet to create a task sheet.
2. Think of the task content and modify the figure in the task sheet.
   - Grasping target (blue circle) and destination (red circle) are mandatory.
   - Arrows are not needed if there is no movement.
   - Obstacle objects (pink circles) are generally not needed. If you want to increase the difficulty, place graspable objects as obstacle objects on the floor.
3. Copy the competition scene in Unity and create a scene for task creation.
   - Create a separate scene for backup purposes. Place the scene for task creation in the `Assets/AssetStoreTools` folder to prevent it from being accidentally pushed to GitHub due to gitignore settings.
4. Open the scene for task creation in Unity and move the grasping candidate position objects (white cubes).
   - Grasping candidate position objects refer to objects like the following:
     `Layout2019IC01/GraspingCandidatesPositions/GraspingCandidatesPositionXX`
   - Place one of the grasping candidate position objects at the position of the grasping target (blue circle).
   - Move all 13 grasping candidate position objects slightly to prevent hardcoding of grasping. 
   - Move objects on the robot's path that are not intentional obstacle objects to positions where they will not interfere, as they can increase the difficulty.
5. Connect the VR device to the PC, launch SteamVR or Oculus software, and make the VR device ready for use.
6. Follow the Wiki procedure, start Interactive Cleanup in data generation mode (`executionMode = 1`), and perform the pointing gesture generation.
   - Return to the initial position after moving, but be aware that the end position and the start position may appear unnatural if you move too far from the initial position. A slight deviation is not a problem.
7. The task is output to `AvatarMotion01.dat` and `EnvironmentInfo01.json`, so copy and save these files.
   - Be careful as continuous recording will overwrite the files.
8. Start Interactive Cleanup in normal mode (`executionMode = 0`), note down the name of the grasping target, and confirm that the task content is appropriate.
9. Enter the name of the grasping target in the task sheet.

## Task Operation Confirmation

1. Use the Interactive Cleanup scene to confirm the operation of all created tasks.

(There is no need to create a separate scene for official use for Interactive Cleanup as the layout and grasping targets are the same every year)

## Updating the 3D Model List (Object Label List)

The list of 3D models used in each competition is shared with participants in advance via a Google Spreadsheet named Object Label. (e.g., RoboCup AsiaPacific 2021 Object Label)

For example, the following updates will be made:

- Specify the path of the a-like objects from the previous competition
- Add the a-like objects for the current competition
- Add new 3D models if increasing the number of models
- Modify the treatment of existing 3D models (whether they are graspable or not)


<br><br>

# Human Navigation Task Creation Procedure

## Basic Flow of Task Creation

For the basic flow of task creation, please refer to GitHub's [Readme](https://github.com/RoboCupatHomeSim/human-navigation-unity) and [Wiki](https://github.com/RoboCupatHomeSim/human-navigation-unity/wiki/AdvancedExecutionProcedures#how-to-create-new-environments). Confirm whether the layout created is appropriate by following the steps below.

## About Difficulty Adjustment

Before creating tasks, please go through the items related to task difficulty adjustment.

- Currently, the difficulty should be set to easy.
- Ensure sufficient differences in difficulty between trials.
- Large rooms increase the difficulty of navigation.
- Many graspable objects increase the difficulty.
- Few landmark objects for explaining the destination or target object increase the difficulty.
- Tasks that are difficult to explain by humans are considered to have high difficulty.

The difficulty of tasks is adjusted by the following elements:

1. **Room Size:** Large rooms make navigation more difficult.
2. **Number of Graspable Objects:** More objects make it difficult to find a specific target object.
3. **Number of Landmark Objects:** Few landmark objects make navigation more difficult.
4. **Difficulty of Task Explanation:** Explanations that are difficult for humans to understand are considered high in difficulty.

When creating tasks, it is important to adjust these elements so that participants can solve them at a manageable level.

## Task Creation Steps

1. Proceed by creating task files while adding task content sheets to a Google Spreadsheet named "HumanNavigationTask Template." Open the HumanNavigationTask Template while working.

   [Template Here](#Spreadsheets)

   1. Think about the tasks. Decide the ratio of new problems to past problems and create new layouts for new problems. Present two problems from one new layout. Therefore, if creating four new problems, create two new layouts. (As of 2022) At this stage, you only need to conceptualize what kind of layouts to create.
   2. Open the regular [HumanNavi](https://github.com/RoboCupatHomeSim/human-navigation-unity) (not the Cloud version) in the Unity editor.
   3. Copy the competition scene (HumanNavi.unity) in Unity and create a scene for task creation. Name it something like HumanNavi2022.unity. Place the scene for task creation in the `Assets/Competition/HumanNavi/HiddenFiles` folder. The `HiddenFiles` folder is gitignored to prevent accidental pushes to GitHub. Create the `HiddenFiles` folder if it does not exist.
   <div align="center"><img src="./img/make_task/mthn_1.png" width="60%"></div>

   4. Open the scene for task creation in Unity and follow the Wiki procedure to create tasks. Refer to the "Task Creation" sheet in the HumanNavigationTask Template for precautions and other references. Create the layout (furniture and graspable object placement) and destinations.
   5. Create a dummy destination for layout confirmation. Although layouts are notified to participants in advance, create a dummy destination for confirming layouts. The dummy destination is named `destination#00` and placed at the feet of the human avatar. Copy and create it from the existing layout's destinations.
   6. Copy the template sheet to create a task sheet. There are also past problem sheets from previous tasks. Take screenshots of the Unity screen for new layout images.
   7. Create a config file (HumanNaviConfig.json) for operation confirmation. It's easier to modify based on the previous config file. Refer to the Wiki for the config file specification.
   8. Run the scene for task creation to confirm the operation of the planned new problems and past problems. Launch the [sample ROS node](https://github.com/RoboCupatHomeSim/human-navigation-ros#how-to-execute-sample-ros-node) on the ROS side. Confirm whether the task can be cleared as expected and whether the layout itself is normal, including unrelated object grasping and opening and closing of cabinets.
   9. Create Prefabs for the new layout. This is somewhat complex. Create the following two types of Prefabs:
      - Prefab without correct destinations (destination#XX)
        - Name it something like Layout2022HN01#01Layout
        - To be published before the competition
      - Prefab above including correct destinations (destination#XX)
        - Name it something like Layout2022HN01#01
        - To be published after the competition

      Thus, you will create a nested Prefab. Correct destinations (destination#XX) cannot be published, so only the first Prefab is published on GitHub or elsewhere before the competition. The second Prefab is used for the competition and is published after the competition. The method to create two types of Prefabs is as follows:

      - Create a folder for this time under Assets/Competition/HumanNavi. Name it something like Assets/Competition/HumanNavi/IROS2022.

      - Temporarily remove all destinations (other than destination#00) from the layout (such as Layout2022HN01#01).
      <div align="center"><img src="./img/make_task/mthn_2.png" width="60%"></div>

      - Drag and drop the layout (such as Layout2022HN01#01) under the folder for this time to create a layout Prefab.
      <div align="center"><img src="./img/make_task/mthn_3.png" width="60%"></div>

      - Add "Layout" to the name of the created Prefab.
      <div align="center"><img src="./img/make_task/mthn_4.png" width="60%"></div>

      - Return the destinations (destination#XX) to their original positions.
      <div align="center"><img src="./img/make_task/mthn_5.png" width="60%"></div>

      - Drag and drop the layout (such as Layout2022HN01#01) under the HiddenFiles folder to create a layout Prefab. ※In the [Create Prefab or Variant?] window, select [Prefab Variant].
      <div align="center"><img src="./img/make_task/mthn_6.png" width="60%"></div>

      - Remove "Variant" from the name of the created Prefab Variant.
      <div align="center"><img src="./img/make_task/mthn_7.png" width="60%"></div>
      - Repeat for all layouts.


   10. Export unitypackage. Click [Assets]-[Export Package...] and select the created Prefabs to export.
   <div align="center"><img src="./img/make_task/mthn_8.png" width="60%"></div>
   11. Collect the deliverables. The deliverables are the task sheet in the HumanNavigationTask Template, the unitypackage file containing the new layout, and the config file.

## Consolidating All Tasks

- Collect all tasks created individually, including task sheets, unitypackage files containing new layouts, and config files, as mentioned in the steps above.
  1. Collect tasks. Collect all tasks created by participating teams, including task sheets, unitypackage files containing new layouts, and config files.
  2. Consolidate task sheets into one Google Spreadsheet.
  3. Consolidate all tasks into one config file.
  4. Open the regular HumanNavi (not the Cloud version) in the Unity editor.
  5. Copy the competition scene (HumanNavi.unity) in Unity and create a scene for task creation. Name it something like HumanNavi2022.unity. Place the scene for task creation in the `Assets/Competition/HumanNavi/HiddenFiles` folder. The `HiddenFiles` folder is gitignored to prevent accidental pushes to GitHub. Create the `HiddenFiles` folder if it does not exist.
  6. Open the scene for task creation.
  7. Import the unitypackage file containing all new layouts. Importing is possible via [Assets]-[Import Package]-[Custom Package...]. Repeat for all new layouts.
  8. Add new layouts to the scene for task creation. Add new layout Prefabs to the scene by dragging and dropping. Use the Prefabs under the HiddenFiles folder (those containing destination#XX).
  9. Add new layouts to the `HumanNaviSessionManager` attached to Moderator in the Environments section. Increase the size of Environments by the number of layouts to be added and add all new layouts to the Elements.
  <div align="center"><img src="./img/make_task/mthn_9.png" width="60%"></div>
  10. Run the scene for task creation to confirm the operation of planned new problems and past problems. Launch the sample ROS node on the ROS side. Confirm whether the task can be cleared as expected, and whether the layout itself is normal, including unrelated object grasping and opening and closing of cabinets.

## Creating a Unity Scene for Layout Confirmation

Create a Unity scene for participants to confirm new layouts. Do not include correct destinations (destination#XX).

1. Open the regular HumanNavi (not the Cloud version) in the Unity editor.
2. Copy the competition scene (HumanNavi.unity) in Unity and create a scene for layout confirmation. Name it `HumanNavi2022Layout.unity` or similar. Place the scene for layout confirmation under the folder for this time (`Assets/Competition/HumanNavi/IROS2022` or similar).
<div align="center"><img src="./img/make_task/mthn_10.png" width="60%"></div>

3. Open the scene for layout confirmation.
4. Place the Prefab without correct destinations (`Layout2022HN01#01Layout` or similar) in the scene.
<div align="center"><img src="./img/make_task/mthn_11.png" width="60%"></div>

5. If the root GameObject of the added layout is active, uncheck it in the Inspector.
<div align="center"><img src="./img/make_task/mthn_12.png" width="60%"></div>

6. Remove "Layout" from the end of the name of the added layout.
<div align="center"><img src="./img/make_task/mthn_13.png" width="50%"></div>

7. Just to be safe, confirm that only `destination#00` exists for all added layouts.
<div align="center"><img src="./img/make_task/mthn_14.png" width="50%"></div>

8. Add new layouts to the `HumanNaviSessionManager` attached to Moderator in the Environments section. Increase the size of Environments by the number of layouts to be added and add all new layouts to the Elements.
<div align="center"><img src="./img/make_task/mthn_15.png" width="60%"></div>

9. Create a config file (`HumanNaviConfig.json`) for layout confirmation.
   - `sessionTimeLimit` should be 999
   - `recoverUsingScoreFile` should be false
   - `maxNumberOfTrials` should be the number of new layouts (not the number of tasks)
   - In `taskInfoList`, include the new layout information. The target can be any object from GraspableObjects present in the layout, and the destination is fixed as `destination#01`. At this point, it's `destination#01`, not `#00`.
<div align="center"><img src="./img/make_task/mthn_16.png" width="100%"></div>

10. Run the scene for layout confirmation and confirm that an error occurs. Launch the sample ROS node on the ROS side. `destination#01` should not exist, so an error is expected.
11. Correct the layout confirmation config file. Change the destination to `destination#00`.
<div align="center"><img src="./img/make_task/mthn_17.png" width="100%"></div>

12. Run the scene for layout confirmation and perform operation confirmation. Launch the sample ROS node on the ROS side. Confirm whether the layout itself is as expected, including object grasping and opening and closing of cabinets.
13. (When the time comes) Publish the Unity file for layout confirmation on GitHub or elsewhere. The new layouts have a set timing for publication, so publish them when the time comes. The files to be published are as follows:
    - The folder for this time (`Assets/Competition/HumanNavi/IROS2022` or similar)
    - The config file for layout confirmation. Rename the config file to `HumanNaviConfig_NewLayouts.json` and place it in the folder for the config files for this time (`SIGVerseConfig/HumanNavi/sample/IROS2022` or similar).
    <div align="center"><img src="./img/make_task/mthn_18.png" width="100%"></div>

## Confirming the Operation of Tasks

1. Open the Cloud version of [HumanNavi](https://github.com/RoboCupatHomeSim/human-navigation-cloud-unity) for official use in the Unity editor.
2. Import the unitypackage file (containing all new layouts) created previously. This package includes both Prefabs for official use and Prefabs for layout confirmation. Importing is possible via `[Assets]-[Import Package]-[Custom Package...]`.
3. Copy `HumanNavi.unity` and create a Unity scene for official use. Name it something like `HumanNavi2022.unity`. Place the scene for official use in the `Assets/Competition/HumanNavi/HiddenFiles` folder. The `HiddenFiles` folder is gitignored to prevent accidental pushes to GitHub.
4. Open the scene for official use.
5. Add new layouts to the scene for official use. Drag and drop new layout Prefabs into the scene. Use the Prefabs under the HiddenFiles folder (those containing destination#XX).
<div align="center"><img src="./img/make_task/mthn_19.png" width="60%"></div>

6. Add new layouts to the `HumanNaviSessionManager` attached to Moderator in the Environments section. Increase the size of Environments by the number of layouts to be added and add all new layouts to the Elements.
7. Add the Graspables of new layouts to the `PunLauncher` attached to `PunLauncher` in the `RootsOfSyncTarget`. The Cloud version adds Photon features, so there are a few additional steps. Increase the size of `RootsOfSyncTarget` by the number of layouts to be added and add the Graspables object under all new layouts to the Elements.
<div align="center"><img src="./img/make_task/mthn_20.png" width="60%"></div>

8. Click the `[Update Photon Scripts]` button attached to `PunLauncher`. This updates the list of objects to be synchronized. You can see the number of RoomObjects has increased. Objects that move (objects with Rigidbody) such as graspable objects and drawers are automatically retrieved.
<div align="center"><img src="./img/make_task/mthn_21.png" width="80%"></div>

9. Confirm that the PhotonTransformView script is attached. Check that the PhotonTransformView script is attached to all graspable objects under GraspableObjects.
<div align="center"><img src="./img/make_task/mthn_22.png" width="80%"></div>

10. Confirm that the PhotonView script is attached to GraspableObjects. Observable Search automatically adds the graspable objects.
11. Use the scene for official use in Unity to confirm the operation of all created tasks. Since this is an official confirmation, use the built executable file for operation confirmation instead of running it in the Unity editor. Use the config file (`HumanNaviConfig.json`) containing the created tasks. For details on building and creating config files, refer to the document "How to Create Executable Files for Official Use." Since it's the Cloud version, two executable files (one for VR and one for ROS) need to be launched. For details, check the [README](https://github.com/RoboCupatHomeSim/human-navigation-cloud-unity). Launch the sample ROS node on the ROS side. You can perform the operation confirmation on one PC (run the ROS side on VMware and launch two executable files on a Windows PC), but try to use AWS to confirm operations as similar to the official competition as possible. Confirm whether the task can be cleared as expected, including unrelated object grasping and opening and closing of cabinets. Also, specifically for Photon, confirm whether the movements of graspable objects and drawers are synchronized between the server and client sides.
