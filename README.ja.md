# PapaMama Coding

PapaMama coding styleは、シェル（貝殻）の概念を用いてシンプルなドメイン固有言語（DSL）を作成できる、ミニマルなワンライナー型JavaScriptライブラリです。クラム(貝)」(貝の中身、食べかす)と呼ばれる単位で関数を組み合わせることができます。

```javascript
const RFC = (m, F) => (...R) => F = (...c) => R[0](c, R, m) ? F : RFC(m);
```

状態の管理： RFC(Recursive Function Combinator：再帰的な関数コンビネータ)と呼ばれる関数は、最初の引数として初期状態mを受け取ります。この状態は、構成された関数の実行を通じて管理したいオブジェクトやその他のデータ型とすることができます。

関数の合成： 第2引数Fは、構成された関数のプレースホルダーであり、後で返される関数を通じて「Crum：クラム」として供給される。RFC関数は、残りのパラメータ...Rで表される任意の数の "Crum"を引数として取る新しい関数を返します。

関数の実行： このF関数は、"Crum "関数を実行し、状態を管理する責任を負います。Crum関数が真を返せば、F関数が返され、そうでなければ、更新された状態mでRFC関数が再び呼ばれることになります。

このコーディングスタイルは、簡潔で柔軟なコードを実現し、1行で状態を管理し機能を構成する独自の方法を可能にします。


# クラム　C.R.U.M. (Collection of Resumable Units and Memory)
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


このコードは、PapaMamaフレームワークのC.R.U.M. (Collection of Resumable Units and Memory：再生可能なユニットとメモリの集合)の基本構文を示したものです。以下、各パーツの説明です：

const RFC = (m, F) => (...R) => (F = (...c) => (R[0](c, R, m) ? F : RFC(m))); defines the RFC (Recursive Function Combinator). 連想配列mと関数Fを引数にとり、関数を再帰的に呼び出す機能を備えています。

SHELL = RFC({a: 1})はシェルを作り、プロパティaを含む連想配列をmに渡します。これはシェルのコンテキストにおけるaの値を含みます。

LOG = (c, R, m) => {...} は、LOG関数（Shell関数またはHead Crumb）を定義しています。この関数は、引数c、R、mを受け取り、それらをコンソールに出力する。最後に、trueを返します。

((c, R, m) => 1) から ((c, R, m) => 4) までの部分は、4つの無名関数（CRUM）を定義しており、それぞれ1〜4の整数を返す単純な関数です。



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

このコードでは、"xeyes "という名前のサンプルを作成します。まず、createCanvas(500, 500)を使ってsetup関数を定義し、canvasを作成します。RFC関数を用いて、LTR_storeという関数の状態を保存する関数を定義しています。この状態オブジェクトは、Crum Hashと呼ばれます。

次に、Circle関数が定義され、与えられた座標と半径を使って円を描画する。setFocus関数は、マウスの位置を追跡してCrum Hashに格納します。DISTANCE関数は、2つの座標間の距離を計算し、新しい座標を返します。

そして、Preservedと呼ばれる名前付きステップが追加します。例えば、xeyesというPreservedでは、背景色が設定され、2つの大きな白い円と2つの小さな黒い円が描かれています。この小さな円は、マウスの位置に応じて動きます。また、ligという名前のPreservedには、フレーム数といくつかのテキストを描画します。

最後に、LTR_exec関数を使って、Crum Hashを更新しながら、指定された名前の関数を実行します。この結果、xeyesとligという2つの異なるPreservedが順番に実行されることになります。

このサンプルは、マウスの位置によって目が動く顔を表現しています。また、Crum Hashを利用して関数間で状態を共有・更新することで、より複雑なアニメーションやインタラクションを実現することができます。

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

このコードでは、GlueSHELL関数を使用しています。GlueSHELL関数は、RFC関数を用いて定義され、クラムハッシュmを引数として受け取ります。このクラムハッシュmは、アニメーションの状態を保存・更新するステートオブジェクトになります。

GlueSHELL関数の内部では、glueという変数に関数が割り当てられています。このglue関数は、「シーリング：封入」と呼ばれる処理によって、アニメーションのセットアップと描画機能を実行する役割を担っています。シーリングとは、変数を囲んで外部からアクセスできないようにする処理のことです。この例では、eval(k)がglue関数内で実行され、kにアニメーションのコードが格納されています。そして、draw関数とsetup関数が存在する場合は、それぞれD配列とS配列に追加されます。

GlueSHELL関数を使用することで、異なるアニメーションコードを個別に実行し、1つのアニメーションにまとめることができます。また、cealingを使用することで、アニメーション間の変数の衝突や干渉を回避することができます。これにより、独立した複数のアニメーションを定義し、それらを組み合わせることで複雑な表現を実現することができます。

https://editor.p5js.org/setapolo/sketches/aLi9ZyWOb


![papamamalogo](https://github.com/setapolo/RFC/blob/main/Screen%20Shot%202023-04-30%20at%2014.02.13.png "logo")
