---
layout: project
type: project
image: img/mm-thumb.png
title: "Manoa Mentoring"
date: 2024
published: true
labels:
  - Meteor
  - MongoDB
  - React/Bootstrap
  - Website
summary: "A website that allows students to work together to achieve success in their academics."
---

<p align="center">
  <img width="800px" class="rounded pe-4" src="../img/manoa-mentoring.png">
</p>

## Overview
Manoa Mentoring is a web application where UH students can join study sessions to aid each other in their academics. Those signing up for the site can distinguish themselves as students or mentors. Users will be able to create and join study sessions on a particular topic. 

### Features
- A page to view all profiles of students and mentors (Contacts such as emails are displayed for communication)
- A page to manage and view all of the study sessions that you joined or created
- A calendar to view all the sessions that the user joined
- A leveling system to track the amount of activity you've done on the site. 

### My Contributions
- Code and Design for the registration page
- Code and Design for the login page
- Code and Design for the profile creation page
- Created profile collection that holds all users profile data (ex: First Name, Last Name, School Year, etc.)
- Created the level system that computes and displays the user's level

The link to site can be found here: [Manoa Mentoring](https://manoa-mentoring.site/)
Project Page is found [here](https://manoa-mentoring.github.io/).

Below is the LevelSystem.js file. It is the brain that computes the user's level data.
```cpp
// Function to calculate the level up threshold based on the user's level
function threshold(userId) {
  // Get user info
  const profile = Profiles.collection.findOne({ owner: userId });

  if (profile) {
    const currentLevel = profile.level;
    let levelUpThreshold = 100; // Base threshold for level 1

    // Calculate level up threshold based on current level
    for (let i = 1; i < currentLevel; i++) {
      levelUpThreshold = Math.ceil(levelUpThreshold * 1.5); // Increase threshold by 1.5 times
    }

    return levelUpThreshold;
  }
  return null;
}

// Function to update user's level and experience points
function LevelSystem(userId, exp) {
  // Get user info
  const profile = Profiles.collection.findOne({ owner: userId });
  console.log(profile);

  if (profile) {
    const currentLevel = profile.level;
    const currentExp = profile.exp;

    let newExp = currentExp + exp;
    let newLevel = currentLevel;
    let levelUpThreshold = threshold(userId); // Calculate level up threshold using the exported function

    // Check if new exp reaches or surpasses level up threshold
    while (newExp >= levelUpThreshold) {
      newLevel++;
      newExp -= levelUpThreshold; // Reduce exp by the level up threshold

      // Update level up threshold for the next level
      levelUpThreshold = Math.ceil(levelUpThreshold * 1.5);
    }

    // Update the user's profile with new level and exp
    Profiles.collection.update(profile._id, { $set: { level: newLevel, exp: newExp } });
  } else {
    // Handle case where user profile is not found (optional)
    console.log('User profile not found for ID:', userId);
  }
}
```
