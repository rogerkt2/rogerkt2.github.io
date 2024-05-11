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
  <img width="500px" class="rounded pe-4" src="../img/manoa-mentoring.png">
</p>

Near the end of my Fall 2023 semester, I had a group project where we were tasked to program a hotel management system in C++. In this hotel management system, we had to create menu for users to use. In this menu, users have a variety of options such as check-in, check-out, create room, delete room, and more. The hotel management system keeps track of what rooms are available while holding data on a room's details (comfort level, size, etc). 

Here is code for searchCustomer() and checkOutRoom() function my group and I created:

```cpp
//Iterate through the guests and find if the guest's name matches the inputed name or an error if there is no match found 
void searchCustomer(const vector<Customer>& guests) {
    string userName;
    cout << "Enter Customer Name: ";
    cin.ignore();  // Ignore newline character left in the buffer
    getline(cin, userName);

      for(int i = 0; i < guests.size(); i++){
        if(userName == guests[i].getName()){
          guests[i].displayCustomerDetails();
          return;
        }
      }
      cout << "Customer not found" << endl;
}
//Checks a guest out of a room by iterating through the guest and room vectors to find if the correct guest and room, then removes the guest from the room and marks the room as available
void checkOutRoom(vector<Customer>& guests, vector<Room>& rooms) {
    int roomNumber, numDays, roomIndex = -1, guestIndex = -1;
    cout << "Enter Room Number: ";
    cin >> roomNumber;
  //checks to see if room number matches the guest's room number and the rooms room number
    for(int i = 0; i < guests.size(); i++){
      if(roomNumber == guests[i].getRoomNumber()){
        guestIndex = i;
        break;
      }
    }
    for(int j = 0; j < rooms.size(); j++){
      if(rooms[j].getNumber() == roomNumber){
        roomIndex = j;
      }
    }
        cout << "Enter length of stay: ";
        cin >> numDays;
      //displays the customer's information and amount due
        guests[guestIndex].displayCheckOutDetails(rooms[roomIndex].getRent() * numDays);

        // Mark the room as available
        rooms[roomIndex].unbook();

}
```
