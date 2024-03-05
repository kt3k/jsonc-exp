An experiment to use jsr in npm module

# Usage

Set `.npmrc` with:

```
@jsr:registry=https://npm.jsr.io
```

And then:

```
npm install @kt3k/jsonc
```

This installs the module with the dependency to [jsr:@std/jsonc](https://jsr.io/@std/jsonc).

Now use can import `parse` from the module, which is actually implemented in [@std/jsonc](https://github.com/denoland/deno_std/blob/021323eba6a3a7aa79c8735943ac6baf249d5a99/jsonc/parse.ts)

```js
import { parse } from "@kt3k/jsonc";

const obj = parse(`{
  // comment
  "foo": 42,
  "bar": 43, // <- trailing comma
}`);

console.log(obj);
```

Save this as `test.mjs`, and it executes like:

```
$ node test.mjs
{ foo: 42, bar: 43 }
```
