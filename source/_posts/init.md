---
title: Holax, Sekai!
date: 2017-08-31 12:40:00
---

各种语言代码高亮的集中测试, 大部分来自[`Highlight.JS`的DEMO](https://highlightjs.org)和[洛谷OJ题目P1001](https://luogu.com.cn/problem/P1001)的样例。

~~没有什么可以抄的代码请放心, 所以也别想着 <kbd>Ctrl+O</kbd> <kbd>Ctrl+C</kbd> <kbd>Ctrl+V</kbd> <kbd>Ctrl+S</kbd> <kbd>Ctrl+W</kbd> 一套连招之类的。~~

```cpp
#include<iostream>
using namespace std;
void NTT(int *A, int type) {
    for (int i = 0; i < limit; ++i) if (i < r[i]) swap(A[i], A[r[i]]);
    for (int mid = 1; mid < limit; mid <<= 1) {
        ll Wn = poww(type == 1 ? G : Gi, mid << 1);
        for (int R = mid << 1, j = 0; j < limit; j += R) {
            ll w=1;
            for(int k = 0; k < mid; k++, w = mul(Wn, w)) {
                int x = A[j + k], y = A[j + mid + k];
                A[j + k] = add(x, y);
                A[j + k + mid]=dec(x, y);
            }
        }
    }
    if(type == -1) {
        for(int Inv = poww(limit, mod - 2), i = 0; i < limit; ++i) {
            A[i] = mul(A[i], Inv);
        }
    }
}
int main()
{
cout<<"                ********    "<<endl;
cout<<"               ************    "<<endl;
cout<<"               ####....#.    "<<endl;
cout<<"             #..###.....##....    "<<endl;
cout<<"             ###.......######              ###            ###    "<<endl;
cout<<"                ...........               #...#          #...#    "<<endl;
cout<<"               ##*#######                 #.#.#          #.#.#    "<<endl;
cout<<"            ####*******######             #.#.#          #.#.#    "<<endl;
cout<<"           ...#***.****.*###....          #...#          #...#    "<<endl;
cout<<"           ....**********##.....           ###            ###    "<<endl;
cout<<"           ....****    *****....    "<<endl;
cout<<"             ####        ####    "<<endl;
cout<<"           ######        ######    "<<endl;
cout<<"##############################################################    "<<endl;
cout<<"#...#......#.##...#......#.##...#......#.##------------------#    "<<endl;
cout<<"###########################################------------------#    "<<endl;
cout<<"#..#....#....##..#....#....##..#....#....#####################    "<<endl;
cout<<"##########################################    #----------#    "<<endl;
cout<<"#.....#......##.....#......##.....#......#    #----------#    "<<endl;
cout<<"##########################################    #----------#    "<<endl;
cout<<"#.#..#....#..##.#..#....#..##.#..#....#..#    #----------#    "<<endl;
cout<<"##########################################    ############    "<<endl;
    return 0;
}
```

<!-- more -->

## Plaintext

```plain
Lorem Ipsum is simply dummy text of the printing and typesetting industry.
```
    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.

## Diff

```diff
Index: languages/ini.js
===================================================================
--- languages/ini.js    (revision 199)
+++ languages/ini.js    (revision 200)
@@ -1,8 +1,7 @@
 hljs.LANGUAGES.ini =
 {
   case_insensitive: true,
-  defaultMode:
-  {
+  defaultMode: {
     contains: ['comment', 'title', 'setting'],
     illegal: '[^\\s]'
   },

*** /path/to/original timestamp
--- /path/to/new      timestamp
***************
*** 1,3 ****
--- 1,9 ----
+ This is an important
+ notice! It should
+ therefore be located at
+ the beginning of this
+ document!

! compress the size of the
! changes.

  It is important to spell
```

## Rust

```rust
#[derive(Debug)]
pub enum State {
    Start,
    Transient,
    Closed,
}

impl From<&'a str> for State {
    fn from(s: &'a str) -> Self {
        match s {
            "start" => State::Start,
            "closed" => State::Closed,
            _ => unreachable!(),
        }
    }
}
```
```rust
use std::io;

fn main(){
    let mut input=String::new();
    io::stdin().read_line(&mut input).unwrap();
    let mut s=input.trim().split(' ');

    let a:i32=s.next().unwrap()
               .parse().unwrap();
    let b:i32=s.next().unwrap()
               .parse().unwrap();
    println!("{}",a+b);
}
```

## JSON (with Comments)

```json
[
  {
    "title": "apples",
    "count": [12000, 20000],
    "description": {"text": "...", "sensitive": false}
  },
  {
    "title": "oranges",
    "count": [17500, null],
    "description": {"text": "...", "sensitive": false}
  }
]
```

## HTML

```html
<!DOCTYPE html>
<title>Title</title>

<style>body {width: 500px;}</style>

<script type="application/javascript">
  function $init() {return true;}
</script>

<body>
  <p checked class="title" id='title'>Title</p>
  <!-- here goes the rest of the page -->
</body>
```

## JavaScript / Node.JS

```javascript
function $initHighlight(block, cls) {
  try {
    if (cls.search(/\bno\-highlight\b/) != -1)
      return process(block, true, 0x0F) +
             ` class="${cls}"`;
  } catch (e) {
    /* handle exception */
  }
  for (var i = 0 / 2; i < classes.length; i++) {
    if (checkCondition(classes[i]) === undefined)
      console.log('undefined');
  }

  return (
    <div>
      <web-component>{block}</web-component>
    </div>
  )
}

export $initHighlight;
```
```js
const fs = require('fs')
const data = fs.readFileSync('/dev/stdin')
const result = data.toString('ascii').trim().split(' ').map(x => parseInt(x)).reduce((a, b) => a + b, 0)
console.log(result)
process.exit()
```

## SQL

```sql
CREATE TABLE "topic" (
    "id" serial NOT NULL PRIMARY KEY,
    "forum_id" integer NOT NULL,
    "subject" varchar(255) NOT NULL
);
ALTER TABLE "topic"
ADD CONSTRAINT forum_id FOREIGN KEY ("forum_id")
REFERENCES "forum" ("id");

-- Initials
insert into "topic" ("forum_id", "subject")
values (2, 'D''artagnian');
```

## Objective-C

```objectivec
#import <UIKit/UIKit.h>
#import "Dependency.h"

@protocol WorldDataSource
@optional
- (NSString*)worldName;
@required
- (BOOL)allowsToLive;
@end

@property (nonatomic, readonly) NSString *title;
- (IBAction) show;
@end
```

## Java

```java
/**
 * @author John Smith <john.smith@example.com>
*/
package l2f.gameserver.model;

public abstract class L2Char extends L2Object {
  public static final Short ERROR = 0x0001;

  public void moveTo(int x, int y, int z) {
    _ai = null;
    log("Should not be called");
    if (1 > 5) { // wtf!?
      return;
    }
  }
}
```
```java
import java.io.*;
import java.util.*;
public class Main {
    public static void main(String args[]) throws Exception {
        Scanner cin=new Scanner(System.in);
        int a = cin.nextInt(), b = cin.nextInt();
        System.out.println(a+b);
    }
}
```

## Swift

```swift
import Foundation

@objc class Person: Entity {
  var name: String!
  var age:  Int!

  init(name: String, age: Int) {
    /* /* ... */ */
  }

  // Return a descriptive string for this person
  func description(offset: Int = 0) -> String {
    return "\(name) is \(age + offset) years old"
  }
}
```

## CSS

```css
@font-face {
  font-family: Chunkfive; src: url('Chunkfive.otf');
}

body, .usertext {
  color: #F0F0F0; background: #600;
  font-family: Chunkfive, sans;
}

@import url(print.css);
@media print {
  a[href^=http]::after {
    content: attr(href)
  }
}
```

## Ruby

```ruby
# The Greeter class
class Greeter
  def initialize(name)
    @name = name.capitalize
  end

  def salute
    puts "Hello #{@name}!"
  end
end

g = Greeter.new("world")
g.salute
```
```ruby
a, b = gets.split.map(&:to_i)
print a+b
```

## Makefile

```makefile
# Makefile

BUILDDIR      = _build
EXTRAS       ?= $(BUILDDIR)/extras

.PHONY: main clean

main:
	@echo "Building main facility..."
	build_main $(BUILDDIR)

clean:
	rm -rf $(BUILDDIR)/*
```

## Go

```go
package main

import "fmt"

func main() {
    ch := make(chan float64)
    ch <- 1.0e10    // magic number
    x, ok := <- ch
    defer fmt.Println(`exitting now\`)
    go println(len("hello world!"))
    return
}
```
```go
package main

import "fmt"

func main() {
    var a, b int
    fmt.Scanf("%d%d", &a, &b)
    fmt.Println(a+b)
}
```

## Bash

```bash
#!/bin/bash

###### CONFIG
ACCEPTED_HOSTS="/root/.hag_accepted.conf"
BE_VERBOSE=false

if [ "$UID" -ne 0 ]
then
  echo "Superuser rights required"
  exit 2
fi

genApacheConf(){
  echo -e "# Host ${HOME_DIR}$1/$2 :"
}
```

## TOML / INI

```ini
; boilerplate
[package]
name = "some_name"
authors = ["Author"]
description = "This is \
a description"

[[lib]]
name = ${NAME}
default = True
auto = no
counter = 1_000
```

## R

```r
library(ggplot2)

centre <- function(x, type, ...) {
  switch(type,
         mean = mean(x),
         median = median(x),
         trimmed = mean(x, trim = .1))
}

myVar1
myVar.2
data$x
foo "bar" baz
# test "test"
"test # test"

(123) (1) (10) (0.1) (.2) (1e-7)
(1.2e+7) (2e) (3e+10) (0x0) (0xa)
(0xabcdef1234567890) (123L) (1L)
(0x10L) (10000000L) (1e6L) (1.1L)
(1e-3L) (4123.381E-10i)
(3.) (3.E10) # BUG: .E10 should be part of number

# Numbers in some different contexts
1L
0x40
.234
3.
1L + 30
plot(cars, xlim=20)
plot(cars, xlim=0x20)
foo<-30
my.data.3 <- read() # not a number
c(1,2,3)
1%%2

"this is a quote that spans
multiple lines
\"

is this still a quote? it should be.
# even still!

" # now we're done.

'same for
single quotes #'

# keywords
NULL, NA, TRUE, FALSE, Inf, NaN, NA_integer_,
NA_real_, NA_character_, NA_complex_, function,
while, repeat, for, if, in, else, next, break,
..., ..1, ..2

# not keywords
the quick brown fox jumped over the lazy dogs
null na true false inf nan na_integer_ na_real_
na_character_ na_complex_ Function While Repeat
For If In Else Next Break .. .... "NULL" `NULL` 'NULL'

# operators
+, -, *, /, %%, ^, >, >=, <, <=, ==, !=, !, &, |, ~,
->, <-, <<-, $, :, ::

# infix operator
foo %union% bar
%"test"%
`"test"`
```

## Scilab

```scilab
// A comment
function I = foo(dims, varargin)
  d=[1; matrix(dims(1:$-1),-1,1)]
  for i=1:size(varargin)
    if varargin(i)==[] then
       I=[],
       return;
    end
  end
endfunction

b = cos(a) + cosh(a);
bar_matrix = [ "Hello", "world" ];
foo_matrix = [1, 2, 3; 4, 5, 6];
```

## Matlab

```matlab
n = 20; % number of points
points = [random('unid', 100, n, 1), random('unid', 100, n, 1)];
len = zeros(1, n - 1);
points = sortrows(points);
%% Initial set of points
plot(points(:,1),points(:,2));
for i = 1: n-1
    len(i) = points(i + 1, 1) - points(i, 1);
end
while(max(len) > 2 * min(len))
    [d, i] = max(len);
    k = on_margin(points, i, d, -1);
    m = on_margin(points, i + 1, d, 1);
    xm = 0; ym = 0;
%% New point
    if(i == 1 || i + 1 == n)
        xm = mean(points([i,i+1],1))
        ym = mean(points([i,i+1],2))
    else
        [xm, ym] = dlg1(points([k, i, i + 1, m], 1), ...
            points([k, i, i + 1, m], 2))
    end

    points = [ points(1:i, :); [xm, ym]; points(i + 1:end, :)];
end

%{
    This is a block comment. Please ignore me.
%}

function [net] = get_fit_network(inputs, targets)
    % Create Network
    numHiddenNeurons = 20;  % Adjust as desired
    net = newfit(inputs,targets,numHiddenNeurons);
    net.trainParam.goal = 0.01;
    net.trainParam.epochs = 1000;
    % Train and Apply Network
    [net,tr] = train(net,inputs,targets);
end

foo_matrix = [1, 2, 3; 4, 5, 6]''';
foo_cell = {1, 2, 3; 4, 5, 6}''.'.';

cell2flatten = {1,2,3,4,5};
flattenedcell = cat(1, cell2flatten{:});
```

## Fortran

```fortran
subroutine test_sub(k)
    implicit none

  !===============================
  !   This is a test subroutine
  !===============================

    integer, intent(in)           :: k
    double precision, allocatable :: a(:)
    integer, parameter            :: nmax=10
    integer                       :: i

    allocate (a(nmax))

    do i=1,nmax
      a(i) = dble(i)*5.d0
    enddo

    print *, 'Hello world'
    write (*,*) a(:)

end subroutine test_sub
```

## Python

```py CNN-Training with Keras https://github.com/keras-team/keras/blob/master/examples/mnist_cnn.py MNIST_CNN
'''Trains a simple convnet on the MNIST dataset.
Gets to 99.25% test accuracy after 12 epochs
(there is still a lot of margin for parameter tuning).
16 seconds per epoch on a GRID K520 GPU.
'''

from __future__ import print_function

import requests
import bs4

import numpy as np
import scipy, sympy
import pandas as pd

import matplotlib as mpl, matplotlib.pyplot as plt
mpl.style.use("seaborn")

import keras
from keras import backend as T

class Constants(object):
    BATCH_SIZE = 128
    NUM_CLASSES = 10
    NUM_EPOCHES = 12
    INPUT_IMG = {
        "DIM_ROWS": 28, # input image dimensions
        "DIM_COLS": 28,
        "SHAPE": (1, 28, 28) if T.image_data_format() == "channels_first" else (28, 28, 1)
    }
    pass

class ImgData(object):

    def __init__(self, src):

        # the data, split between train and test sets
        self.__xtrain = src[0][0]
        self.__ytrain = keras.utils.to_categorical(src[0][1], Constants.NUM_CLASSES)    # convert class vectors to binary class matrices
        self.__xtest = src[1][0]
        self.__ytest = keras.utils.to_categorical(src[1][1], Constants.NUM_CLASSES)     # 把标签处理成 one-hot 型数据

        # 考虑到Theano和TensorFlow两个框架的数据结构不同, 于此需要根据不同的后端调整数据维度顺序
        if T.image_data_format() == "channels_first":
            self.__xtrain = self.__xtrain.reshape(
                self.__xtrain.shape[0],
                1,
                Constants.INPUT_IMG["DIM_ROWS"],
                Constants.INPUT_IMG["DIM_COLS"],
            ).astype("float32") / 255
            self.__xtest = self.__xtest.reshape(
                self.__xtest.shape[0],
                1,
                Constants.INPUT_IMG["DIM_ROWS"],
                Constants.INPUT_IMG["DIM_COLS"],
            ).astype("float32") / 255

        else:
            self.__xtrain = self.__xtrain.reshape(
                self.__xtrain.shape[0],
                Constants.INPUT_IMG["DIM_ROWS"],
                Constants.INPUT_IMG["DIM_COLS"],
                1,
            ).astype("float32") / 255
            self.__xtest = self.__xtest.reshape(
                self.__xtest.shape[0],
                Constants.INPUT_IMG["DIM_ROWS"],
                Constants.INPUT_IMG["DIM_COLS"],
                1,
            ).astype("float32") / 255

        return

    def log_datashape(self):
        print("X Shape: %s" % self.__xtrain.shape[ 1 : ])
        print("Training on %s Data, Validating on %s." % (self.__xtrain.shape[0], self.__xtest.shape[0]))
        return

    @property
    def xtrain(self):
        return self.__xtrain

    @property
    def ytrain(self):
        return self.__ytrain

    @property
    def xtest(self):
        return self.__xtest

    @property
    def ytest(self):
        return self.__ytest

    pass

if __name__ == "__main__":

    data = ImgData(keras.datasets.mnist.load_data())

    # 创建一个 Sequential 模型, 并把所有涉及的计算层按顺序投入其中
    seq = keras.models.Sequential(layers = [
        keras.layers.convolutional.Conv2D(
            32,
            kernel_size = (3, 3),
            activation = "relu",
            input_shape = Constants.INPUT_IMG["SHAPE"]
        ),
        keras.layers.convolutional.Conv2D(64, (3, 3), activation="relu"),
        keras.layers.pooling.MaxPooling2D(pool_size=(2, 2)),
        keras.layers.core.Dropout(rate=0.25),
        keras.layers.core.Flatten(),
        keras.layers.core.Dense(units=128, activation="relu"),
        keras.layers.core.Dropout(rate=0.5),
        keras.layers.core.Dense(units=Constants.NUM_CLASSES, activation="softmax")
    ])

    # 架构并编译模型, 同时声明模型计算的 loss(损失函数), optimizer(优化器), metric(评价算法)
    seq.compile(
        loss=keras.losses.categorical_crossentropy,
        optimizer=keras.optimizers.Adadelta(),
        metrics=["accuracy"]
    )

    # 拟合数据, 训练模型
    history = seq.fit(
        x = data.xtrain,
        y = data.ytrain,
        batch_size = Constants.BATCH_SIZE,
        epochs = Constants.NUM_EPOCHES,
        verbose = 1,
        validation_data = (data.xtest, data.ytest)
    )

    # 评估模型
    _eval = seq.evaluate(x=data.xtest, y=data.ytest, verbose=0)
    print("Test Loss: %s" % _eval[0])
    print("Test Accuracy: %s" % _eval[1])

    pass
```