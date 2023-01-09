<!--
 * @Author: Ada J
 * @Date: 2023-01-09 15:41:45
 * @LastEditTime: 2023-01-09 16:13:35
 * @Description: 
-->
# Some special characteristics in TS

* Any type is any intersection with any kind, that is, `1 & any` result is `any`, and `any` type can be determined by this attribute.

  ```ts
  type IsAny<T> = 'dong' extends ('guang' & T) ? true : false
  ```
* When the union type appears as a type parameter to the left of the conditional type, it is scattered into a single type passed in and finally merged.

  ```ts
  type IsUnion<A, B = A> =
      A extends A
          ? [B] extends [A]
              ? false
              : true
          : never
  ```

* When **never appears as a type parameter to the left of the condition type**, `never` is returned directly.

  ```ts
  // type TestNever<never> = never 
  type TestNever<T> = T extends number ? 1 : 2;

  // use this to test never
  type IsNever<T> = [T] extends [never] ? true : false
  ```

* When **any appears as a type parameter to the left of the conditional type**, it directly returns the union type of `trueType` and `falseType`.

  ```ts
  type TestAny<T> = T extends number ? 1 : 2;
  // TestAny<any> = 1|2
  ```
* The tuple type is also an array type, but length is a `numeric literal`, and the length of an array is `number`. It can be used to determine the tuple type.

  ```ts
  type IsTuple<T> = 
      T extends [...params: infer Eles] 
          ? NotEqual<Eles['length'], number> 
          : false

  type NotEqual<A, B> = 
      (<T>() => T extends A ? 1 : 2) extends (<T>() => T extends B ? 1 : 2)
          ? false : true;
  ```

* **Inversion** occurs at **function parameters** and can be used to implement `union` type to `intersection` type.

  ```ts
  type UnionToIntersection<U> = 
      (U extends U ? (x: U) => unknown : never) extends (x: infer R) => unknown
          ? R
          : never
  ```
* The index of the optional index may not have it, then the after `Pick` may be `{}`, which can be used to filter optional indexes, and vice versa.

  ```ts
  type Pick<T, K extends keyof T> = { [P in K]: T[P]; }

  type GetOptional<Obj extends  Record<string, any>> = {
      [
          Key in keyof Obj 
              as {} extends Pick<Obj, Key> ? Key : never
      ] : Obj[Key];
  }
  ```
* The index type of index is a `string literal` type, while indexable signatures are not, and indexable signatures can be filtered out with this feature.

  ```ts
  type RemoveIndexSignature<Obj extends Record<string, any>> = {
    [
        Key in keyof Obj 
            as Key extends `${infer Str}`? Str : never
    ]: Obj[Key]
  }
  ```

* `Keyof` can only get the `public` index of the class, which can be used to filter out the `public` attribute.


* The **default derivation** by `infer` is not a `literal` type, using `as const` can get the `literal` type, but with `readonly` decoration, so that the pattern matching must also add `readonly`.

  ```ts
  const arr2 = [1, 2, 3] as const;

  type arrType2 = typeof arr2;

  type ReverseArr<Arr> = Arr extends readonly [infer A, infer B, infer C] ? [C, B, A] : never;

  type ReverseArrRes = ReverseArr<arrType2>;
  ```
