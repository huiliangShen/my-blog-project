---
title: 'JS深入浅出之数据类型'
---

标签： JS

---

### 1. **JS的原始类型**
```
number          //let a = 1;
string          //let a = '123';
boolean         //let a = false;
null            //let a = null;
undefined       //let a = undefined;
Object => {
    Function    //let a = function(){};
    Array       //let a = [1,2,3];
    Date        //let a = new Date();
    ...
}
```
以上的6种数据类型就是JS内最重要也是最常用的类型！接下来本文为着重讲下JS类型的判断，因JS语言特效，它可以任意转化为其他的类型，而实际生产过程中，我们需要判断出得到的数据类型到底是什么！所以了解这些东西也是非常有必要的！
<!--more-->
### 2. **JS种的== 与 === 的区别**

```
关于 ===
类型不同直接返回false
类型相同：
        null === null
        undefined === undefined
        NaN ！=NaN
        new Object ！= new Object
类型相同，同===
关于 ==
类型不同，尝试类型转换和比较：
    null == undefined相同
    number == string 转number 1=="1.0"//true
    boolean == ? 转number 1==true//true
    Object == number | string 尝试对象转为基本类型 new String('hi') == 'hi'//true
```
### 3. **JS中的类型判断**
```
typeof
instanceof
Object.prototype.toString.apply();
```
我们主要使用以上三种来判断数据类型，当然这三种方式各有优缺点！
```
typeof
    typeof 100 'number'
    typeof true  'boolean'
    typeof function 'function'
    typeof (undefined) 'undefined'
    typeof new Object() 'Object'
    typeof [1,2]    'Object'
    typeof NaN 'number'
    typeof null 'Object'
    //typeof:适合基本类型及function检测，遇到null失效
```

```
instanceof
    100 instanceof Number //true
    window instanceof Object //true
    //instanceof:适合自定义对象，也可以用来检测原生对象，在不同的iframe和window间检测时失效
```
```
Object.prototype.toString.apply();
    Object.prototype.toString.apply([1,2,3]);//"[object Array]"
    // Class:通过{}.toString拿到，适合内置对象和基元类型，遇到null和undefined失效（IE678等返回[object,Object]）
```
希望更深入了解这些内容的，请移步至 [慕课网JS深入浅出](http://www.imooc.com/code/5760) 的链接。

    本文纯属代表个人观点，如有错误，请见谅=。=