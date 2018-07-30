## Day 09 - Chrome Dev Tools and Console Tricks

### Using Chrome Dev Tools and Cool Console Tricks.

### Challenge Solution

1. Clear the console
```
console.clear();
```

2. Regular console
```
console.log("Hello World");
```

3. Interpolated Console log
```
const food = "pizza";
console.log("I like %s!",food);
console.log(`I like ${food}!!`);
```

4. Styled Console log
```
console.log("%c hi there ","font-size:32px;font-family:tahoma;color:white;background:red");
```

5. Console warning
```
console.warn("This is warning");
```

6. Console Error
```
console.error("This is error");
```

7. Console info
```
console.info("This is info");
```

8. Testing with console
```
console.assert(1===2,"This will run for failed assert condition.");
```

9. View DOM Elements with console
```
const para = document.querySelector("p");
console.log(para);
console.dir(para);
```

10. Grouping with console 
```
const dogs = [{ name: 'Snickers', age: 2 }, { name: 'hugo', age: 8 }];
dogs.forEach((dog) => {
    console.groupCollapsed(`${dog.name}`);
    console.log(`Dog's name is : ${dog.name}`);
    console.log(`Dog's age is : ${dog.age}`);
    console.log(`Dog's double age is : ${dog.age*2}`);
    console.groupEnd(`${dog.name}`);
})
```

11. Console count
```
console.count("happy");
console.count("happy");
console.count("happy");
console.count("happy");
```

12. Measure time taken to perform an operation with console
```
console.time('timeToFetchUsers');
fetch('https://jsonplaceholder.typicode.com/users')
    .then( (response) => response.json())
    .then( (users) => {
    console.timeEnd('timeToFetchUsers');
        console.log(users);
    });
```
