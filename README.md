# ts-index
Collection of typescript DIY lessons



### Index

- Create a cli app : https://github.com/typescript-school/ts-cli-app
- Add jest tests : https://github.com/typescript-school/ts-jest
- Events: https://github.com/typescript-school/ts-events
- Streams with typescript : https://github.com/typescript-school/ts-cli-app



### Todo : 

- [ ] Event loop in depth

  - Refere : 
    - https://www.educative.io/edpresso/what-is-the-event-loop-in-nodejs
    - https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick/#check

  - [ ] `setImmediate()` vs `process.nextTick()`

    - refer: https://stackoverflow.com/a/15349865/1065020
    - https://stackoverflow.com/a/42030923/1065020

    ```
    import fs from 'fs';
    import http from 'http';
    
    const options = {
      host: 'www.stackoverflow.com',
      port: 80,
      path: '/index.html'
    };
    
    describe('deferredExecution', () => {
      it('deferredExecution', (done) => {
        console.log('Start');
        setTimeout(() => console.log('TO1'), 0);
        setImmediate(() => console.log('IM1'));
        process.nextTick(() => console.log('NT1'));
        setImmediate(() => console.log('IM2'));
        process.nextTick(() => console.log('NT2'));
        http.get(options, () => console.log('IO1'));
        fs.readdir(process.cwd(), () => console.log('IO2'));
        setImmediate(() => console.log('IM3'));
        process.nextTick(() => console.log('NT3'));
        setImmediate(() => console.log('IM4'));
        fs.readdir(process.cwd(), () => console.log('IO3'));
        console.log('Done');
        setTimeout(done, 1500);
      });
    });
    ```

    

- [ ] Implementing `Promise` 

