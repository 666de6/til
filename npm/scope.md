<!--
 * @Author: Ada J
 * @Date: 2022-09-20 10:11:01
 * @LastEditTime: 2022-09-20 10:35:52
 * @Description: 
-->
# How to publish a scoped package in private registry and install it from multiple registry?

## publish
### add a scope
Change value of "name" field in your package.json to add a scoped name, such as
```js
{
  "name": "@my-scope/packageName"
}
```
or, you can also use npm cli command to add a scope
```bash
npm init --scope=@my-scope
```
### publish
```bash
npm login
```
```bash
npm publish
```
## install
### set multiple registry
You have two ways to do it, see below
#### use npm cli
Associating a scope with a registry
```bash
npm config set @my-scope:registry http://reg.example.com/
```
Set fallback registry for others
```bash
npm config set registry https://registry.npmjs.org/
```
or use nrm
```bash
nrm use npm
```
#### config in .npmrc
```bash
@my-scope:registry=http://reg.example.com/
registry=https://registry.npmjs.org/
````

After this, when you install packages, packages that contain the scope "@my-scope" will be installed from the specific registry, and others will be installed from that fallback registry.

