# Gamification Concept — OWL Learning

The design of a gamification system for the OWL e-learning platform at PT Krakatau Posco. Gamification is designed as a **feature embedded in the learning flow** — not a separate menu — so learners stay motivated to learn regularly and complete materials to the end.

**Status:** concept completed (November 2026); not yet implemented in code.

<!-- Once screenshots are added to the images/ folder, remove this comment.
     Files referenced below: dashboard-gamification.png, level-tree.png,
     popup-leaderboard.png, popup-quest.png -->

## Concept Summary

- The system uses a single type of point: **EXP**. Total EXP determines a learner's level and tree stage.
- There are **10 levels**; each level is one stage of tree growth, from Seed of Knowledge (Level 1) to Mighty OWL Tree (Level 10, 32,000 EXP).
- EXP is earned from learning activities, daily and weekly missions, and badges.
- **Check-in** is done by clicking the Check-in button; one click counts as one check-in day and one **streak** day.
- There are daily and weekly **Bonus Chests**, as well as **Streak Freeze** to protect a learner's streak.
- There are **16 permanent badges**; each badge grants a +25 EXP bonus and is calculated from the learner's learning data from the very beginning (retroactive).
- The **weekly leaderboard** is ranked by the EXP earned during the current week.

## Levels & Tree Stages

| Level | Tree Stage | Minimum EXP |
|---|---|---|
| 1 | Seed of Knowledge | 0 |
| 2 | First Sprout | 100 |
| 3 | Green Seedling | 250 |
| 4 | Sturdy Sapling | 500 |
| 5 | Young Tree | 1,000 |
| 6 | Lush Canopy Tree | 2,000 |
| 7 | Deep-Rooted Tree | 4,000 |
| 8 | Blossoming Tree | 8,000 |
| 9 | Fruit-Bearing Tree | 16,000 |
| 10 | Mighty OWL Tree | 32,000 |

## How to Earn EXP

EXP comes from three layers:

1. **Base activities** — learning activities that automatically grant EXP, for example: completing content (+10), submitting a task on time (+20), completing a playlist (+40), earning a course certificate (+50), daily check-in (+5).
2. **Missions** — daily and weekly quests grant bonus EXP on top of the base activity EXP:
   - Daily: complete 1 content item (+30), complete a post-test (+50), pass a post-test with a score of 90 or more (+30), leave a comment (+10)
   - Weekly: complete 1 playlist (+200), check in on 4 days in a week (+90)
3. **Badges** — each unlocked badge grants +25 EXP.

## Bonus Chests & Streak Freeze

- The **Daily Chest** unlocks when all daily quests are completed in one day; it contains bonus EXP and/or a Streak Freeze.
- The **Weekly Chest** unlocks when both weekly missions are completed; it contains +75 EXP and 1 Streak Freeze.
- **Streak Freeze** protects a streak: it is used automatically when a learner misses 1 check-in day, so the streak does not break. Freezes are earned from the Daily Chest or the 7-day streak milestone, and the count resets every month.

## Badges & Achievements

The 16 badges are grouped into 4 categories: **Completion** (The First, Quick Finisher, Playlist Finisher, Playlist Master, Certified, Certificate Collector), **Grades** (Perfectionist, Quiz Master, Sharp Shooter, Top Scorer), **Consistency** (On Time Learner, Learning Marathon, Streak Master), and **Achievement** (10-Hour Milestone, 50-Hour Milestone, Legend Learner). All badges are permanent and retroactive.

## Placement in the LMS

- **Home:** a summary of level, EXP, streak, and daily missions.
- **My Learning:** the **Learning Journey** tab contains the level profile and tree, the leaderboard, badges, and the full missions; details are shown as pop-ups (leaderboard, badge list, how to earn EXP, mission details).

## Screenshots

![Gamification Dashboard](images/dashboard-gamification.png)
*Gamification dashboard in the Learning Journey tab*

![Levels & Tree Stages](images/level-tree.png)
*The 10 tree-growth level stages*

![Leaderboard Pop-up](images/popup-leaderboard.png)
*Weekly leaderboard pop-up*

![Quest Pop-up](images/popup-quest.png)
*Daily and weekly mission pop-up*
