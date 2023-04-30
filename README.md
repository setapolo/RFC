# PapaMama Coding

PapaMama coding style is a minimalistic one-liner JavaScript library that enables you to create a simple domain-specific language (DSL) using the concept of shells (like seashells). You can combine features in units called "crums(clams)" (the inside of the shell or scrap things).

```javascript
const RFC = (m, F) => (...R) => F = (...c) => R[0](c, R, m) ? F : RFC(m);
```

State management: The RFC(Recursive Function Combinator) function takes an initial state m as its first argument. This state can be an object or any other data type that you want to manage throughout the execution of the composed functions.

Function composition: The second argument F is a placeholder for the composed functions, which are supplied later as "Crums" through the returned function. The RFC function returns a new function that takes any number of "Crum" as its arguments, represented by the rest parameter ...R.

Function execution: The returned function creates a new function F that takes a "Crum" as its argument, represented by the rest parameter ...c. This F function is then responsible for executing the "Crum" function and managing the state. If the "Crum" function returns true, the F function is returned; otherwise, the RFC function is called again with the updated state m.

This coding style allows for concise and flexible code, as well as a unique way of managing state and composing functionality in a single line. 


# C.R.U.M. (Collection of Resumable Units and Memory)
```javascript
const RFC=(m,F)=>(...R)=>(F=(...c)=>(R[0](c,R,m)?F:RFC(m)));
SHELL=RFC({a:1})
(LOG=(c,R,m)=>{
  console.log.apply(R,[c,R,m].map(_=>[_,_.toString()]));
  return true},{param1:1},{pram2:2})
((c,R,m)=>1)
((c,R,m)=>2)
((c,R,m)=>3)
((c,R,m)=>4)
();
```


This code demonstrates the basic syntax of the PapaMama framework's C.R.U.M. (Collection of Resumable Units and Memory). Below is an explanation of each part:

const RFC = (m, F) => (...R) => (F = (...c) => (R[0](c, R, m) ? F : RFC(m))); defines the RFC (Recursive Function Combinator). It takes an associative array m and a function F as arguments and provides the ability to call functions recursively.

SHELL = RFC({a: 1}) creates a shell and passes an associative array containing the property a to m. This includes the value of a in the shell's context.
LOG = (c, R, m) => {...} defines the LOG function (Shell function or Head Crumb). This function takes the arguments c, R, and m, and outputs them to the console. Finally, it returns true.

The parts from ((c, R, m) => 1) to ((c, R, m) => 4) define four anonymous functions (CRUMs), each being simple functions that return integers from 1 to 4.



![papamamalogo](https://github.com/setapolo/RFC/blob/main/Screen%20Shot%202023-04-30%20at%2014.02.13.png "logo")
