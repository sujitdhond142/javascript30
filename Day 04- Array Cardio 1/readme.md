## Day 04 - Array Cardio 1

### Javascript Array methods like *filter()*, *sort()*, *reduce()*.

### Challenge Solution

1. Filter inventors who were born in 1500s
```
inventors.filter( (inventor) => {
    return inventor.year>=1500 && inventor.year<1600
});
```

2. Give names of inventors' first and last name
```
inventors.map( (inventor) => `${inventor.first} ${inventor.last}`);
```

3. Sort inventors by birthdate
```
inventors.sort( (a,b) => a.year>b.year ? 1 : -1);
```

4. How many years did all inventors live
```
const totalYears = inventors.reduce((year,inventor) => {
    return year+inventor.passed-inventor.year
},0);
```

5. Sort inventors by years lived
```
inventors.sort(function(a,b){
    return (a.passed-a.year) > (b.passed-b.year) ? 1 : -1;
});
```
    // 6. create a list of Boulevards in Paris that contain 'de' anywhere in the name

6. Create list of Boulevards in Paris that contain 'de' anywhere in the name from [this page](https://en.wikipedia.org/wiki/Category:Boulevards_in_Paris)
```
const category = document.querySelector(".mw-category");
// convert nodelist to array
const links = Array.from(category.querySelectorAll("a"));
const list = links.map((link) => link.innerText)
                  .filter((link) => link.includes('de'));
```

7. Sort people alphabetically by last name
```
people.sort(function(a,b){
    const [aLast,aFirst] = a.split(',');
    const [bLast,bFirst] = b.split(',');
    return aLast>bLast?1:-1;
})
```

8. Sum up instances of each element
```
const data2 = data.reduce(function(object,item){
    if(!object[item]){
        object[item]=0;
    }
    object[item]+=1;
    return object;
},{});
```
