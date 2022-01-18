# 목차
[Log](#Log)    
[Keyboard Event](#Keyboard-Event)    
[Iterate key value object list](#Iterate-key-value-object-list)    

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

## Iterate key value object list

key - value 형태의 object list를 반복하여 value 값을 뽑아내는 방법이다.

사용할 데이터는 `vBasic` 이라고 명했으며 내부 데이터는 다음과 같다

```jsx
console.log(JSON.stringify(vBasic)); 		// 데이터 조회
// 결과 :  {"aKey":"", "bKey":"", "cKey":"X", "dKey":"X", "eKey":"", "fKey":""}
```

`for(key in object)` 방식을 사용하여 object 내부의 key - value 항목들을 순회한다.

아래 코드는 object를 순회하면서 해당 value가 ‘X’인지 확인하는 것이다.

```jsx
var isChked = false;
for(key in vBasic){   // vBasic의 key들을 하나씩 가져옴
	console.log(vBasic[key]); // 가져온 key를 통해 value를 확인
	if(vBasic[key] == 'X'){		
		isChked = true;
		break;
	}
}
```