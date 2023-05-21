# PapaMama Coding

PapaMama coding style is a minimalistic one-liner JavaScript library that enables you to create a simple domain-specific language (DSL) using the concept of shells (like seashells). You can combine features in units called "crums(clams)" (the inside of the shell or scrap things).

```javascript
const RFC = (m, F) => (...R) => F = (...c) => R[0](c, R, m) ? F : RFC(m);
```

State management: The RFC(Recursive Function Combinator) function takes an initial state m as its first argument. This state can be an object or any other data type that you want to manage throughout the execution of the composed functions.

Function composition: The second argument F is a placeholder for the composed functions, which are supplied later as "Crums" through the returned function. The RFC function returns a new function that takes any number of "Crum" as its arguments, represented by the rest parameter ...R.

Function execution: The returned function creates a new function F that takes a "Crum" as its argument, represented by the rest parameter ...c. This F function is then responsible for executing the "Crum" function and managing the state. If the "Crum" function returns true, the F function is returned; otherwise, the RFC function is called again with the updated state m.

This coding style allows for concise and flexible code, as well as a unique way of managing state and composing functionality in a single line. 

# Hello World
```javascript
//papamam Hello,world
"use strict;";
const RFC=(m,F)=>(...R)=>(F=(...c)=>(R[0](c,R,m)?F:RFC(m)));
RFC({ i:0,
      p:(k,R,m)=>console.log(k?k.p:0,R,m),
      base:(c,R,m)=>{
        const {0:k}=c;const {1:r}=R;let {i:i}=m;
        r?("cmd" in r)?m[r.cmd]?m[r.cmd](k,R,m):console.log(i):0:0;
        Object.assign(m,{i:++i});
        return k?k:!Object.assign(m,{...r});
      }
    })
    ((c,R,m)=>m.base(c,R,m),{cmd:"p"})
      ({p:"Hello,"})({p:"world"})()
    ((c,R,m)=>m.base(c,R,m),{cmd:"p"})
      ({p:"Hello,"})({p:"world#2"})()
```
This script is a simple "Hello, world" example using a higher-order function, RFC. The RFC function is a recursive function that accepts an initial state m and a function F and returns a new function that awaits further arguments R.

The RFC function: This function takes a state object m and a closure F as arguments. It returns a new function that awaits further arguments R. When these arguments are provided, the closure R[0] is executed.

The state object m: This object initially holds i:0 and two functions p and base. p is a function that prints the p property of its argument k. base is a function that performs operations based on its arguments c, R, and m. Specifically, if the second element r of R exists and r has a property cmd, it executes the function corresponding to cmd.

The first closure passed to RFC: This closure invokes the base function in m. The object {cmd:"p"} passed next triggers the execution of the p function in m, and its result is printed.

The objects {p:"Hello,"}, {p:"world"}, {p:"Hello,"}, and {p:"world#2"} passed next: These objects are passed to the RFC function, but what kind of operation they perform depends on the base function. In this code, unless there is a cmd property in base, no operation is defined for these objects.

In summary, the script defines a recursive higher-order function RFC, which encapsulates a simple logic that prints a string based on the command cmd provided. In this case, the command p prints the p property of the given object. The script then executes the function with the arguments that contain the string "Hello, world" in their p properties.

https://editor.p5js.org/setapolo/sketches/cvUKGUJL2

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


# xeyes demo / Crum Hash and Preserved 
```javascript
"use strict;";
setup=_=>createCanvas(500,500);
const RFC=(m,F)=>(...R)=>(F=(...c)=>(R[0](c,R,m)?F:RFC(m)));
RFC([])(LTR_store=(c,R,m)=>{
  const store=_=>{
    const head=_.shift();
    R[1][head[0].name]=[];
    Object.assign(R[1][head[0].name],_);
    _.length=0;
  };
  c[0]?m.push(c):store(m);
  return true;
},window)
({name:"bootstrup"})
(Circle=(c,R,m)=>{
  Object.assign(m,c[1][1]);
  fill(m["fill"]);
  circle(m.x,m.y,m.r)
})
(setForcus=(c,R,m)=>[{dx:mouseX,dy:mouseY}][0])
(DISTANCE =(c,R,m) => {
        let {ox:ox,oy:oy,dx:dx,dy:dy}=m;
        const d=createVector(ox,oy);
        const o=createVector(m.dx,m.dy);
        const e=o.copy().sub(d).mult(30 * 0.3 / d.dist(o)).add(d);
        return {x:e.x,y:e.y}
})()
({name:"xeyes"})
(c=>{background(c[1][1]["fill"])},{fill:200})
((c,R,m)=>[{x:20,y:30,r:30}][0])
(Circle,{fill:255})
((c,R,m)=>[{x:50,y:30,r:30}][0])
(Circle,{fill:255})
((c,R,m)=>[{x:50,y:30,r:9}][0])
(setForcus)
((c,R,m)=>[{ox:50,oy:30}][0])
(DISTANCE)
(Circle,{fill:0})
((c,R,m)=>[{ox:20,oy:30}][0])
(DISTANCE)
(Circle,{fill:0})
()
({name:"lig"})
((c,R,m)=>{text(frameCount,10,80);return {xx:21}},555)
((c,R,m)=>{text(c[1][1]["text"],10,90);return {yy:22}},{text:"this is delete"})
((c,R,m)=>{text(m.yy,10,100);return {zz:23}},777)
();

RFC([])(LTR_exec=(c,R,m)=>{
  let M={};
  const exec=(c,R,m)=>{
    const ret=c[0](c,R,m);
    Object.assign(m,ret);
    Object.assign(m.m,ret);
    return true
  }
  c[0]?m.push(c):0;
  draw=z=>m.map((_,i)=>{
    let a=[];
    Object.assign(a,R[1][_[0]]);
    a.unshift([exec]);
    a.unshift([{a:i,m:M}]);
    a.unshift([RFC]);
    a.reduce((p,c,i,a)=>[p[0](c[0],c,_)]);
  });
  return true;  
},window)("xeyes","j")("lig","k")();
```

This code creates a sample called "xeyes". First, the setup function is defined using createCanvas(500, 500) to create a canvas. The RFC function is used to define a function called LTR_store, which stores the state of the functions. This state object is called Crum Hash.

Next, the Circle function is defined, which draws a circle using the given coordinates and radius. The setFocus function tracks the position of the mouse and stores it in the Crum Hash. The DISTANCE function calculates the distance between two coordinates and returns a new coordinate.

Then, named steps called Preserved are added. For example, in the Preserved named xeyes, the background color is set, and two large white circles and two small black circles are drawn. These small circles move according to the position of the mouse. Also, in the Preserved named lig, the frame count and some text are drawn.

Finally, the LTR_exec function is used to execute the functions with the specified names while updating the Crum Hash. This results in the execution of the two different Preserved, xeyes and lig, in sequence.

This sample represents a face with eyes that move according to the position of the mouse. In addition, the Crum Hash is used to share and update the state between functions, enabling more complex animations and interactions.

https://editor.p5js.org/setapolo/sketches/4FZVlkh7r

# sealing and codefusion

```javascript
"use strict;";
const RFC = (m, F) => (...R) => (F = (...c) => (R[0](c, R, m) ? F : RFC(m)));
const GlueSHELL = RFC({t:0,S:[],D:[]})((c, R, m) => {
  const [k, n] = [c.shift(), { ...m }];
  let { t: t ,D:D,S:S} = n;
  if(!t){
    setup=_=>S.map(_=>_())
    draw=_=>D.map(_=>_());    
  }
  if(k&&!c[0]){
    const glue=((_,draw,setup,window)=>{//"cealing" the variables
        eval(k);
        draw?D.unshift(draw):0;setup?S.unshift(setup):0
      });
    glue();    
  }
  t++;
  Object.assign(m, { t: t });
  return true;
})
(`
r=6;
setup=_=>{createCanvas(500,500);colorMode(HSB);background(0);rectMode(CENTER);noStroke();}
draw=_=>{for(y=0;y<height;y+=40)for(x=0;x<width;x+=40){fill(random(10,100),60,99);rect(20+x+random(-r,r),20+y+random(-r,r),20,20);}}
//https://twitter.com/yoshiyuki_hongo/status/1644249232973627394
`)
(`
p=z=x=y=d=a=f=0,draw=t=>{for(f++||createCanvas(w=255,w),p++,j=-1;j<w;y=2*j++/w-1)for(i=-1;i<w;x=2*i++/w-1,d=sqrt(x*x+y*y),z=int(w*cos(a=atan2(y,x))/d+p)^int(w*sin(a)/d+p))set(i,j,color(d,z&w,z&w));updatePixels()};
//https://twitter.com/PilEmmanuel/status/1565684837511569409
`);
```

In this code, the GlueSHELL function is used. The GlueSHELL function is defined using the RFC function and takes the crum hash m as an argument. This crumb hash m is a state object that stores and updates the state of the animation.

Inside the GlueSHELL function, a variable named glue is assigned a function. This glue function is responsible for executing the setup and draw functions of the animation through a process called "sealing". Sealing refers to the process of enclosing variables, making them inaccessible from the outside. In this example, eval(k) is executed within the glue function, with k containing the animation code. Then, if the draw and setup functions exist, they are added to the D and S arrays, respectively.

By using the GlueSHELL function, different animation codes can be executed individually and combined into a single animation. Additionally, by using cealing, variable conflicts and interference between animations can be avoided. This allows for defining multiple independent animations and combining them to achieve complex expressions.

https://editor.p5js.org/setapolo/sketches/aLi9ZyWOb


![papamamalogo](https://github.com/setapolo/RFC/blob/main/Screen%20Shot%202023-04-30%20at%2014.02.13.png "logo")
