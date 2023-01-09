<!--
 * @Author: Ada J
 * @Date: 2023-01-09 13:45:09
 * @LastEditTime: 2023-01-09 14:57:43
 * @Description: 
-->
# Reconstruct and transform

TypeScript's `type`, `infer`, and variables declared by `type parameters` cannot be modified, and you need to reconstruct new types if you want to make various transformations on the type to produce new types.Such as:

```js
type Push<Arr extends  unknown[], Ele> = [...Arr, Ele];
```

```js
type CapitalizeStr<Str extends string> = 
    Str extends `${infer First}${infer Rest}` 
        ? `${Uppercase<First>}${Rest}` : Str;
```

```js
type CamelCase<Str extends string> = 
    Str extends `${infer Left}_${infer Right}${infer Rest}`
        ? `${Left}${Uppercase<Right>}${CamelCase<Rest>}`
        : Str;
```

```js
type AppendArgument<Func extends Function, Arg> = 
    Func extends (...args: infer Args) => infer ReturnType 
        ? (...args: [...Args, Arg]) => ReturnType : never;
```

```js
type UppercaseKey<Obj extends Record<string, any>> = { 
    [Key in keyof Obj as Uppercase<Key & string>]: Obj[Key]
}
```