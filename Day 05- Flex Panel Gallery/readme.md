## Day 05 - Flex Panel Gallery

### Panels gallery with flex and javascript.

### Challenge Solution

1. We need to display panels in flex.
```
.panels {
    display:flex;
}
```
2. Each individual panel also be displayed as flex.
```
.panel {
    display: flex;
    flex:1;
    justify-content: center;
    flex-direction: column;
}
```
3. Flex width should grow from 1 to 5 after clicking it.
```
.panel.open {
    flex:5;
}
```
4. Each child element should be in flex for better alignment.
```
.panel > * {
    flex: 1 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
}
```
5. Upper and lower paragraph text needs be translated.
```
.panel > *:first-child{
    transform: translateY(-100%);
}
.panel > *:last-child{
    transform: translateY(100%);
}
.panel.open-active > *:first-child,
.panel.open-active > *:last-child{
    transform: translateY(0);
}
```
6. Add js to toggle open and open-active class
```
document.querySelectorAll('.panel').forEach((panel) => {

    panel.addEventListener('click',function(){
        panel.classList.toggle('open');
    })
    
    panel.addEventListener('transitionend',function(e){
        if(e.propertyName.includes('flex')){
            panel.classList.toggle('open-active');
        }
    })
});
```
