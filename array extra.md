문제 1. 배열을 입력받아, 해당 배열에 들어있는 요소들 중 최대값을 찾는 함수를 작성하세요. (루프를 이용하세요)

예:

```js
max([3, 1, 4, 5, 2]) // -> 5

const biggest = (arr) => {
  let conArr = []
  for(let i = 0; i < arr.length; i++) {
    if(arr[i-1] < arr[i]) {
      conArr.push(arr[i])
    } 
  } return conArr[conArr.length-1]
}
biggest([7,15,9,20,12]);
```


---

문제 2. 배열을 입력받아, 해당 배열에 들어있는 요소들 중 최대값을 찾는 함수를 작성하세요. (`Array.prototype.reduce`를 이용하세요)

```js
function max(arr) {
  // reduce를 쓸 때
  // '누적값의 역할'이 무엇인지 잘 정하는 것이 중요하다.
  // 누적값: 지금까지 봤던 숫자 중에 제일 큰 수
  return arr.reduce((acc, item) => {
    // 안에 들어있는 함수의 반환값이, 다음단계의 누적값이 된다. 
    if(acc > item) {
      return acc 
    } else {
      return item
    }
  }, -infinity) // -infinity로 어떤 음수가 와도 아무런 문제없이 최대값을 구할 수 있다. 
}
max([3,1,4,5,2])

```

---

문제 3. 2차원 배열을 입력받아 1차원 배열로 바꾸는 함수를 작성하세요. (루프를 이용하세요)

예:

```js
flatten([
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]) // -> [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
```js
const flatten = (arr) => {
  return String(arr).split(',').map(Number)
}
flatten([[1, 2, 3], [4, 5, 6], [7, 8, 9]])


const flatten = (arr) => {
  container = []
  flatReduce = arr.reduce((acc, item) => acc + item) // 1,2,34,5,67,8,9 (초기값은 안줌)
  flatReduceArr = flatReduce.split('') // [ '1', ',', '2', ',', '3', '4', ',', '5', ',', '6', '7', ',', '8', ',', '9' ]
  for(let i = 0; i < flatReduceArr.length; i++) {
    if(!(flatReduceArr[i] === ',')) {
      container.push(flatReduceArr[i]) // [ '1', '2', '3', '4', '5', '6', '7', '8', '9' ]
    }
  } return container.map(Number)
}
flatten([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
```
---

문제 4. 2차원 배열을 입력받아 1차원 배열로 바꾸는 함수를 작성하세요. (`Array.prototype.reduce`를 이용하세요)
```js
const flatten = (arr) => {
  container = []
  flatReduce = arr.reduce((acc, item) => acc + item)
  flatReduceArr = flatReduce.split('')
  for(let i = 0; i < flatReduceArr.length; i++) {
    if(!(flatReduceArr[i] === ',')) {
      container.push(flatReduceArr[i])
    }
  } return container.map(Number)
}
flatten([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
```
---

문제 5. (3 * 3) 빙고 판이 배열에 저장되어 있습니다. 빙고인 경우 `true`, 아니면 `false`를 반환하는 함수를 작성하세요. (단, 칸이 비어있는 경우는 0, 칸이 채워져 있는 경우는 1로 표현합니다.)

예:

```js
bingo([
  [0, 1, 0],
  [0, 1, 1],
  [0, 0, 1]
]) // -> false

bingo([
  [1, 1, 0],
  [0, 1, 1],
  [0, 0, 1]
]) // -> true

bingo([
  [0, 1, 0],
  [0, 1, 1],
  [0, 1, 1]
]) // -> true
```

---

문제 6. (9 * 9) 오목 판이 배열에 저장되어 있습니다. 흑이 이긴 경우 1, 백이 이긴 경우 2, 아무도 이기지 않은 경우 0을 반환하는 함수를 작성하세요. (단, 칸이 비어있는 경우는 0, 흑은 1, 백은 2로 표현합니다.)

예:

```js
omok([
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 1, 0, 0, 0, 2, 0, 0,]
  [0, 0, 0, 1, 0, 0, 2, 0, 0,]
  [0, 0, 0, 0, 1, 0, 2, 0, 0,]
  [0, 0, 0, 0, 0, 1, 2, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
]) // -> 0

omok([
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 1, 0, 0, 0, 2, 0, 0,]
  [0, 0, 0, 1, 0, 0, 2, 0, 0,]
  [0, 0, 0, 0, 1, 0, 2, 0, 0,]
  [0, 0, 0, 0, 0, 1, 2, 0, 0,]
  [0, 0, 0, 0, 0, 0, 1, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
]) // -> 1

omok([
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 1, 0, 0, 0, 2, 0, 0,]
  [0, 0, 0, 1, 0, 0, 2, 0, 0,]
  [0, 0, 0, 0, 1, 0, 2, 0, 0,]
  [0, 0, 0, 0, 0, 1, 2, 0, 0,]
  [0, 0, 0, 0, 0, 0, 2, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
  [0, 0, 0, 0, 0, 0, 0, 0, 0,]
]) // -> 2
```

---

문제 7. 배열을 입력받아 있는 요소 중 아무거나 하나를 골라서 반환하는 함수를 작성하세요.

예:

```js
randomItem([1, 2, 3, 4, 5]) // 1, 2, 3, 4, 5 중 아무거나 반환
```
```js
const randomItem = (arr) => {
  return arr[Math.floor(Math.random()*arr.length-1)+1]
}
randomItem([1,2,3,4,5])
```
---

문제 8. 배열을 입력받아, 요소들의 순서를 뒤섞은 새 배열을 반환하는 함수를 작성하세요. (단, 원본 배열이 변경되어서는 안 됩니다.)

예:

```js
shuffle([1, 2, 3, 4, 5]) // [3, 1, 4, 5, 2] 와 같이 순서가 뒤섞인 새 배열 반환
```
```js
const shuffle = (arr) => {
  arrCopy = arr.slice(0);
  for(let i = arrCopy.length-1; 0 < i; i--) {
    let j = Math.floor(Math.random() * i ) + 1;
    let temp = arrCopy[i];
    arrCopy[i] = arrCopy[j];
    arrCopy[j] = temp
  }
  return arrCopy;
}
shuffle([1,2,3,4,5])
```