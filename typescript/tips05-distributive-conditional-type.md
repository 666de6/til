<!--
 * @Author: Ada J
 * @Date: 2023-01-09 15:27:43
 * @LastEditTime: 2023-01-09 15:37:52
 * @Description: 
-->
# The distributive of union type

Each type in a union type is independent of each other, and TypeScript has made special treatment for it, that is, **when encountering string types and conditional types, each type will be passed in separately for calculation, and finally the calculation results of each type will be combined into a union type**.

There are two points in particular:

* A extends A is not meaningless, the meaning is to take a single type from the union type and put it into A

* A extends A is a distributed conditional type, [A] extends [A] is not, only the left side is a separate type parameter.



```ts
type BEM<
    Block extends string,
    Element extends string[],
    Modifiers extends string[]
> = `${Block}__${Element[number]}--${Modifiers[number]}`;
```

```ts
type IsUnion<A, B = A> =
    A extends A
        ? [B] extends [A]
            ? false
            : true
        : never
```

```ts
type UppercaseA<Item extends string> = 
    Item extends 'a' ?  Uppercase<Item> : Item;

type Union = 'a' | 'b' | 'c';

type result = UppercaseA<Union>
```