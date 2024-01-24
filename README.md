# React-16-Tutorial-Notes



1. `npm i create-react-app`
2. `create-react-app  <project_name>`
3. `cd <project_name>`  and  `npm start`
4. strict mode is enabled by default in React
5. every function in javascript is an object.


6. important sample related to `this`:

example1:
```javascript
const person = {
    name: "zahra",
    walk() {
        console.log(this);
    }
}

person.walk();
```

in this example, `this` references to `person` object.


examlpe2:

```javascript
const person = {
    name: "zahra",
    walk() {
        console.log(this);
    }
}

const walk = person.walk;
walk();
```

in this example, `this` references to global object which is `window`.  please note that if strict-mode is enabled, then the result is `undefined`.

example3:

```javascript
const person = {
    name: "zahra",
    walk() {
        console.log(this);
    }
}

const walk = person.walk.bind(person);
walk();
```

with `bind` method, we changed the `this` reference. now `this` references to `person` object.

As we told, every function in javascript is an object. so on `person.walk` which is a function (so it is an object also) we access on `bind` method and other methods also.


