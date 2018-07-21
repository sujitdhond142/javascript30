## Day 02 - Change CSS variables with JS

### Easily change CSS variable with javascript.

### Challenge Solution
- Add css variable in :root as following:
```
:root{
  --spacing: 10px;
  --base-color: #ffc600;
  --blur: 10px;
}

``` 
- Apply these variable to image and highlight
```
img{
  background-color: var(--base-color);
  padding: var(--spacing);
  filter: blur(var(--blur));
}
.hl{
  color: var(--base-color);
}
```

- Add JS to change css variables
```
document.querySelector("#spacing").addEventListener('input',function(e){
    document.documentElement.style.setProperty("--spacing", e.target.value+e.target.getAttribute('data-sizing'));
});

document.querySelector("#base").addEventListener('input',function(e){
    document.documentElement.style.setProperty("--base-color",e.target.value);
});

document.querySelector("#blur").addEventListener('input',function(e){
    document.documentElement.style.setProperty('--blur',e.target.value+e.target.getAttribute('data-sizing'));
});
```