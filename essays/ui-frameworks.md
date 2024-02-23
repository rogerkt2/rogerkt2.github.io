---
layout: essay
type: essay
title: "Putting My Big Boy Boots on with Frameworks"
# All dates must be YYYY-MM-DD format!
date: 2024-02-22
published: true
labels:
  - HTML
  - CSS
  - Bootstrap 5
  - Reflection
---

## Can't Live in this World Without Standards

Everyone has standards. When it comes to eating, choosing what to wear, who to date, or what to do in the next five minutes, people will have their kind of guidelines for themselves. People's standards could be perceived as high, while some could be seen as low. I, myself, believe that my standards in life are pretty moderate. I do not expect too much from people or things, although my standards for coding are high.

Whenever I code a program, I make sure my code looks neat and easy to read. I check the number of indents under all my loops or if-else statements are correct and consistent. In all honesty, I truly believed that the way I structured my code was supreme until I started coding on IntelliJ. IntelliJ uses a code analysis tool called ESLint that identifies problems with the code and structuring. ESLint skewed with my perception of my coding standards.

## ESLint is Love, ESlint is Life

<img width="150px" class="rounded float-start pe-4" src="../img/ESLintImage.png">
Programming with ESLint enabled was quite an annoying experience. Out of all the programmers in the world, no one has a coding standard as high as ESLint. As soon as I create a new variable, I am met with red lines and an error icon. If I accidentally miss a space between a parenthesis and a curly bracket, I get slapped with a red line and an error icon. This entire experience is very different from my experience with programming on Jsfiddle. Jsfiddle does not yell at you if you type out your code like this: 


```cpp
var dog;
function pets     () {

console.log(

	"I love ");


}
```

If you were to input this code into IntelliJ with ESLint enabled, it would turn into this:

```cpp
const dog = 'dogs';
function pets(animal) {
	console.log('I love ${animal}');
}

console.log(pets(dog));

```

I am not saying that ESLint is horrible to work with. ESLint nags you for a good reason. With ESLint, I will be constantly reminded about the functions or variables I have not used yet, or the spaces that I need to add or delete. It ensures that your code will not have any issues in the long run. ESLint helps you practice structuring your code as well. In time, programming with ESLint will turn you into a programmer with prestige coding standards.
