

specify what `this` means in a method

```typescript
function sayHello(this: HelloEmitter, name: string){
    this.sayHello(name);
}
```

