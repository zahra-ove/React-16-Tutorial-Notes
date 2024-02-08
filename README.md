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


8. spread operator can be used for arrays and objects:


example for object:
```javascript
const first = {"name": "Mosh"};
const second = {"age": 18};

const clone = {...first, ...second};
```

also spread operator can be used for cloning an object:

```javascript
const first = {"name": "Mosh"};
const clone = {...first}
```


9. class in javascript -> name in PascalCase mode

10. `zen coding` techniques:

example: type this line in any IDE : `table.table>thead>tr>th*4` and then press `Tab` on keyboard.

11.the component that owns a piece of the state, should be the one modifying it.


----------------------------------------------------

12. comparison of `state` in class component and functional component in React:

State in Class Components:
    - State Merging: setState() automatically merges the updated state with the existing state.
    - Asynchronous State Updates: State updates in class components might be asynchronous, meaning you can't rely on the state to immediately reflect the changes after calling setState().

State in Functional Components (with Hooks):
    - State Merging: Unlike class components, state updates in functional components don't automatically merge. Instead, you have to manage the merging yourself, usually by spreading the previous state, e.g., setState(prevState => ({ ...prevState, newValue })).
    - Synchronous Updates: State updates in functional components are synchronous. After calling the setter function, the state is immediately updated, and the component re-renders.



----------------------------------------------------

list of all npm packages:
`npm list -g --depth=0`


----------------------------------------------------

in webstorm, install `react snippet` plugin and then for creating `React class component` => type: `rcc` and for creating `React functional compoenent` type: `rsf`.

----------------------------------------------------

در React ما همانند angular  به صورت پیشفرض، router نداریم زیرا  React یک   light weght library است که وظیفه  view rendering رو بر عهده دارد. بنابرابن برای داشتن Router نیاز است یک  third-party  library نصب کنیم به نام   `react-router-dom` با دستور    `npm i react-router-dom`.
همینطوز یک library مشابه داریم به نام   `react-router-native` که برای مباحث موبایل استفاده میشود.

   ----------------------------------------------------



