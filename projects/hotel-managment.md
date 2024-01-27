---
layout: project
type: project
image: img/micromouse/micromouse-square.jpg
title: "Hotel Management System"
date: 2023
published: true
labels:
  - C++
summary: "I worked in a group project where we created a hotel management system in C++"
---

Near the end of my Fall 2023 semester, I had a group project where we were tasked to program a hotel management system in C++. In this hotel management system, we had to create menu for users to use. In this menu, users have a variety of options such as check-in, check-out, create room, delete room, and more. The hotel management system keeps track of what rooms are available while holding data on a room's details (comfort level, size, etc). 

In this group project, I worked

```cpp
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```
