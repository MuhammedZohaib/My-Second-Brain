## Setting Up Development Environment

```node
npm install -g typesctipt
```

```node
tsc -v //Check Version of typescript compiler
```

```node
tsc index.ts //compiling a typescript file
```

### Configuring TypeScript Compiler

We create a typescript configuration file by using
```node
tsc --init
```


```ts
//Types
let price : number = 10;
let name : string = "lmao";
let passed : boolean = true;
let age; //This is type any variable (Avoid declaring any type variables)
```

