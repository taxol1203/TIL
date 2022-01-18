# 목차
[Log](#Log)    
[Keyboard Event](#Keyboard-Event)  

## Log
```js
console.log()
```
### object를 console로 찍는 법
```js
JSON.stringify(myObj)
```

## Keyboard Event
- **onkeydown** : 키를 눌렀을때 이벤트 (shift, alt, controll, capslock 등의 모든 키에 동작한다. 단 한영변환, 한자 등의 특수키는 인식 못한다)
- **onkeyup** : 키를 눌렀다가 땠을 때 이벤트 (onkeydown 에서 인식하는 키들을 인식 한다)
- **onkeypress** : 실제로 글자가 써질때 이벤트 (shift, tap, enter 등의 특수키는 인식 못한다)

