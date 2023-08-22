# TypeScript 核心使用方式

## 使用TypeScript的方式

1. 通过本地下载使用 `npm i typescript -g`
2. 在`[typescriptlang.org/zh/play](http://在typescriptlang.org/zh/play)` 适合学习语法的场景

## 特点

### 类型推断

```tsx
let str = 'abc'
str = 10
```

此处，会报错：

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/41efbafa-b6de-4aca-b000-3d426576bb4d/Untitled.png)

TypeScript会自行推断各个变量的类型

**这种方式的书写并不推荐**

### 类型注解

```tsx
let str: string
str = 'abc'
```

### 类型断言

```tsx
let numArr =[1,2,3]
const result = numArr.find(item => item>2)
result *5
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e6a2eae4-c4c8-4a7b-ac0e-c6145faa9f0f/Untitled.png)

result 返回的值，不一定都能给回数字，可以被计算，有可能是undefined。

当确认，numArr中必然有值大于2，则可以通过类型断言的方式来设置：

```tsx
let numArr =[1,2,3]
const result = numArr.find(item => item>2) as number // 此处就是断言
result *5
```

## 类型

### 单一

```
let v1 = 'abc';
let v2 = 10;
let v3 = true;

let nu = null;
let un = undefined;

let v4 = null; // 联合类型
let v5 = 2; // 数值限定
```

### 数组

```tsx
let arr:number[] = [1,2,3]
let arr1:Array<string> = ['a','b','c']
```

### 元组

```tsx
let t1:[number, string, number] = [1, 'a', 2]
let t2:[number, string, number?] = [1, 'a'] // ？是可选值的意思
```

### 枚举

使用关键字`enum`

```tsx
enum MyEnum{
    A,
    B,
    C
}

console.log(MyEnum.A)
console.log(MyEnum[0])
```

```jsx
"use strict";
var MyEnum;
(function (MyEnum) {
    MyEnum[MyEnum["A"] = 0] = "A";
    MyEnum[MyEnum["B"] = 1] = "B";
    MyEnum[MyEnum["C"] = 2] = "C";
})(MyEnum || (MyEnum = {}));
console.log(MyEnum.A);
console.log(MyEnum[0]);
```

### 空类型

`Void` 关键字，来表示函数的返回值为`undefined`

## 函数

### void

```tsx
function MyFn(a:number, b:string):void{
    return a + b
}
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b2606adf-7853-48d6-9dc9-3346ba078bec/Untitled.png)

### 参数、返回值的设置

```tsx
function MyFn(a:number, b?:number):number{
    return a + b
}
```

### 参数默认值

```tsx
function MyFn(a=10, b?:number, c?boolean, ...rest:number[]):number{
    return 100
}
```

## 接口

```tsx
**interface Obj {
    name:string,
    age:number
}**

const obj:Obj ={
    name:'a',
    age:10
}
```

### 类型别名

```tsx
type MyUsername = string | number

let a:MyUsername
```

### 泛型