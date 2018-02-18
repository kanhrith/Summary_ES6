# Summary_ES6
❖ ES6 Feature  
1. Block scope variables:
In ES6, it went from declaring variable with var to used let/const. 
 let will hoist the variable to the top of the block (NOT at the top of function like ES5).
 Let is a block scoped. We cannot used it, before it declared. 
 We used const, if we don’t want a variable to change at all
2. Template Literals: We don’t have to do more nesting concatenations when we have template literals.
Example:     
  const first = 'kanhrith';
  const last = 'Fz';
  console.log(`Your name is ${first} ${last}.`); 
3.   Multi-line strings:  
We don’t have to concatenate strings + \n. 
Example: 
  const template = `<li …>
  <div class="view">
  <input class="toggle" type="checkbox" [checked]="… ">
  <label></label>
  <button class="submit></button></div>
  <input class="edit" value="">
  </li>`; console.log(template);
4. Destructuring Assignment 
desctructing is very useful and consise:
Getting elements from an arrays: 
  Const  array = [1,2,3,4]; 
  Const [first,third] = array; 
  Consol.log(first,third); 
Swapping values: 
  let a = 1;
  let b = 2; 
  [a, b] = [b, a]; 
  console.log(a, b); 
Multiple return values:
  function margin() {
  const left=1, right=2, top=3, bottom=4;
  return { left, right, top, bottom };
  } 
  const { left, bottom } = margin();
  console.log(left, bottom); // 1 4 
Parameters matching:
  const user = {firstName: 'kanhrith', lastName: 'Fz'}; 
  function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
  }
  console.log(getFullName(user)); 
Deep Matching 
  function settings() {
  return { 
  display: { color: 'red' }, keyboard: { layout: 'querty'} };
  }
  const { display: { color: displayColor }, keyboard: { layout: keyboardLayout }} = settings();
  console.log(displayColor, keyboardLayout);
5. Classes and Objects
In ES6, we have some syntax sugar. We can do the same with less boiler plate and new keywords such as class and constructor. 
We went from “constructor function” to “classes” 
Example: 
  class Animal {   constructor(name) 
  { this.name = name; }
  speak() { console.log(this.name + ' makes a noise.'); }
  }
  const animal = new Animal('animal'); animal.speak(); // animal makes a noise. 
6. Inheritance  
In ES6, we have a new keywords extends and super. 
  class Dog extends Animal {   
  speak() 
  {   super.speak();   
      console.log(this.name + ' Lyy');   }
  } 
  const dog = new Dog('Bos');
  dog.speak(); // Bos makes a noise. // Bos Lyy.
7. Native Promises  
This can get messy pretty quickly if you need a 3rd or 4th callback. Let’s see how we can do it with promises:
function printAfterTimeout(string, timeout){ 
  return new Promise((resolve, reject) => {
  setTimeout(function(){
  resolve(string); }, timeout);
  });
  }
  printAfterTimeout('Hello ', 2e3).then((result) => {
  console.log(result); 
  return printAfterTimeout(result + 'Reader', 2e3); }).then((result) => {
  console.log(result); }); 
8. Arrow functions
ES6 didn’t remove the function expressions but it added a new one called arrow functions. 
Example:
  $('.btn').click((event) =>  this.sendData()); 
  const ids = [291, 288, 984]; 
  const messages = ids.map(value => `ID is ${value}`);
9. For…of 
We went from for to forEach and then to for...of: 
Example:
  const array = ['a', 'b', 'c', 'd'];
  for (const element of array) {
  console.log(element);
  }
10.  Default parameters
We went from checking if the variable was defined to assign a value to default parameters. 
Example: 
  function point(x = 0, y = -1, isFlag = true){  
  console.log(x,y, isFlag);
  }
  point(0, 0) // 0 0 true 
  point(0, 0, false) // 0 0 false 
  point(1) // 1 -1 true point() // 0 -1 true 
11. Rest parameters
We went from arguments to rest parameters and spread operator. We can do the same using the rest operator ... 
Example:
  function printf(format, ...params) { 
  console.log('params: ', params);
  console.log('format: ', format); 
  } 
  printf('%s %d %.2f', 'adrian', 321, Math.PI); 
12. Spread operator
We went from apply() to the spread operator. Again we have ... to the rescue.
Example1:   
  Math.max(...[2,100,1,6,43]) // 100
Example2:
  const array1 = [2,100,1,6,43];
  const array2 = ['a', 'b', 'c', 'd'];
  const array3 = [false, true, null, undefined];
  console.log([...array1, ...array2, ...array3]); 
