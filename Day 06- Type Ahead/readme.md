## Day 06 - Type Ahead

### Type ahead with javascript.

### Challenge Solution

1. Fetch cities and store into a variable
```
const endpoint = 'https://gist.githubusercontent.com/Miserlou/c5cd8364bf9b2420bb29/raw/2bf258763cdddd704f8ffd3ea9a3e81d25e2c6f6/cities.json';

let cities = [];
fetch(endpoint)
  .then((response) => response.json())
  .then((response) => { cities = [...response] });
```

2. Add event listener to search form
```
document.querySelector('.search').addEventListener('input',showResults);
```

3. Filter results which have our search string in them.
```
function findResults(key,cities){
  return cities.filter( place => {
    const regex = new RegExp(key,'gi');
    return place.city.match(regex) || place.city.match(regex);
  });
}
```
4. Show results to users.
```
function showResults(){
  const results = findResults(this.value,cities);
  const html = results.map( place => {
    const regex = new RegExp(this.value,'gi');
    const cityName = place.city.replace(regex,`<span class="hl">${this.value}</span>`);
    const stateName = place.state.replace(regex,`<span class="hl">${this.value}</span>`);
      return `<li>
                <span class="name">${cityName}, ${stateName}</span>
                <span class="population">${numberWithCommas(place.population)}</span>
              </li>`;
    }).join('');
  suggestions.innerHTML = html;
}
```
5. Replace number with formatted string.
```
function numberWithCommas(s){
  return s.toString().replace(/\B(?=(\d{3})+(?!\d))/g,',');
}
``` 
