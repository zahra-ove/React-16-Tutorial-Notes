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



7. object destructuring:

``` javascript
const address  = {
  street: 'street one',
  city: 'NY',
  country: 'US'  
};


const { street, city, country } = address;

console.log(street);
console.log(city);
console.log(country);
```


we could also, extract only specific property from address object:

```javascript
const { street } = address;
console.log(street);
```

also we could change the name of variable by defining an alias for it:

```javascript
const { street:st } = address;
console.log(st);
```




