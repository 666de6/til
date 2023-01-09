<!--
 * @Author: Ada J
 * @Date: 2023-01-09 15:02:44
 * @LastEditTime: 2023-01-09 15:12:24
 * @Description: 
-->
# Recursive to reuse

When encountering **an uncertain number of problems**, you have to reflexively think of **recursion**. For example, the length of the array is uncertain, the length of the string is uncertain, and the number of index type layers is uncertain.

```js
type ReverseStr<
    Str extends string, 
    Result extends string = ''
> = Str extends `${infer First}${infer Rest}` 
    ? ReverseStr<Rest, `${First}${Result}`> 
    : Result;
```

```js
type StringToUnion<Str extends string> = 
    Str extends `${infer First}${infer Rest}`
        ? First | StringToUnion<Rest>
        : never;
```

```js
type ReplaceAll<
    Str extends string, 
    From extends string, 
    To extends string
> = Str extends `${infer Left}${From}${infer Right}`
        ? `${Left}${To}${ReplaceAll<Right, From, To>}`
        : Str;
```