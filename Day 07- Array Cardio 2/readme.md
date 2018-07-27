## Day 07 - Array Cardio 2

### Javascript Array methods like *some()*, *every()*, *find()*, *findIndex()*.

### Challenge Solution

1. Search people for at least one person 19 or older
```
const currentYear = new Date().getFullYear();
const isAtLeastOneAdult = people.some((person) => currentYear-person.year>=19 );
console.log(isAtLeastOneAdult);
```

2. Is everyone 19 or older?
```
const isAllAdults = people.every((person) => currentYear-person.year>=19 );
console.log(isAllAdults);
```

3. Find the comment with the ID of 823423
```
const searchID = 823423;
const singleComment = comments.find((comment) => comment.id==searchID);
console.log(singleComment);
```

4. Delete the comment with the ID of 823423
```
const searchIndex = comments.findIndex((comment) => comment.id==searchID);
comments.splice(searchIndex,1);
console.log(comments);
```
