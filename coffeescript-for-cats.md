## An introduction for new programmers 
### *So easy your human companion could do it too!*

![](images/substack-cats.png)

CoffeeScript is a programming language.
In other words, it is a means to instruct a computer to do things.
Just the same as one controls humans with hisses and meows, one controls computers with statements written in a programming language.
CoffeeScript compiles to JavaScript.
All web browsers understand JavaScript and you can take advantage of that to make web pages do crazy things!

This page will teach you some CoffeeScript basics so that you can get up and running in no time*!

\* *actual time: more than none. Probably an hour or two. Also since you are a cat you are less likely to run and more likely to lay around in the sun*

## Table of contents

- [The Basics](#basics)
- [Strings](#strings)
- [Values and variables](#values)
- [Using functions](#functions)
- [Built in JS functions](#standard-library)
- [Download new JS functions](#third-party-javascript)
- [Writing new functions](#writing-functions)
- [Loops](#loops)
- [Lists](#lists)
- [Objects](#objects)
- [Recommended reading](#recommended-reading)

## Don't be a scaredy-cat

You will always land on your feet &mdash; even when programming! Unlike [pawing over a glass of water](imagehttp://tj.github.com/masteringnode/book.htmls/dealwithit.gif) on your laptop, _nothing_ in these tutorials will damage your computer in any way, even if you mistype a command or click the wrong button. Like cats, computer programmers make mistakes all time: misspelling things, forgetting quotes or brackets, and being forgetful of how basic functions (and yarn) work. Programmers care more about making it work _eventually_ rather than trying to make it work the very first time. The best way to learn is by making mistakes!

So don't be a scaredy-cat! The absolute worst thing that will happen is that you might have to refresh this page in your web browser if you get stuck. Don't worry though, this will happen very rarely &mdash; and we're talkin' 13-toed cat rare.

## <a id="basics" href="#basics">#</a> Basics

Go to [nodejs.org](http://nodejs.org), and click the `Install` button to install node.js.

Then run this command in your terminal to install coffeescript shell:

```
sudo npm install coffee-script
```

Then type `coffee` in the terminal to use the coffeescript shell:

```
coffee>
```

If you don't want to install it on your machine, you can try CoffeeScript online.
Go to [CoffeeScript REPL](http://larryng.github.io/coffeescript-repl/).
And you will see an online CoffeeScript shell in your browser.

CoffeeScript shell a programming language shell, otherwise known as a "console" or "REPL". takes your inputs, evaluates them, then returns the result to you.
Basically it's a way to type one thing at a time into a computer and immediately get the computers answer back.
They are super useful as a learning tool (I still use the console nearly every day that I'm coding).

Try type `1 + 1` into the shell and then hit the `Enter` key and watch what happens.

You will see something like this:


```
coffee> 1+1
2
```

Using this shell is a very important part of learning CoffeeScript.
If you don't know if something works or what the command is for something, go to the console and figure it out!

### <a id="strings" href="#strings">#</a> Strings

Since I am a cat I want to replace every instance of the word `dog` on the Internet with `those blasted dogs`.
First go into your console and type in a few sentences that contain the word `dog` at least once.
In CoffeeScript a bunch of letters, numbers, words or anything else is known as a **String** (as in a *string* of characters). Strings have to begin AND end with a quotation mark. Single `'` or double `"` is fine, just make sure you use the same at the beginning as you do at the end.

```
coffee> "I wish dogs drooled less."
'I wish dogs drooled less.'
coffee> 'Dogs are the bane of my existence.'
'Dogs are the bane of my existence.'
coffee> "We should send all dogs to the moon.'
SyntaxError: missing ", starting
```


See the nasty error message? Don't worry - you didn't break any laws. SyntaxError is just the way it sounds when robots tell you that your program has a problem.
The first two sentences had matching quotation marks at the beginning and end, but when I mixed single and double quotation marks it freaked out on me.

OK, to fix up one of these sentences (by replacing `dog` with our enhanced version) we have to first save the original sentence so that we can call it up later when we do our replacing magic. Notice how the string gets repeated in red when we type it into the shell? This is because we haven't told it to save the sentence anywhere so it just gives it right back (or it gives us an Error back if we messed something up).

### <a id="values" href="#values">#</a> Values and variables

**Values** are the simplest components in CoffeeScript.
`1` is a value, `true` is a value, `"hello"` is a value, `() -> {}` (function) is a value, the list goes on!
There are a handful of different **types** of values in CoffeeScript, but we don't need to go over them all right away &mdash; you will learn them naturally the more you code!

To store values we use things called **variables**.
The word 'variable' means 'can change' and is used because variables can store many different types of values and can change their value many times.
They are pretty much like mailboxes.
We put something in a variable, like our sentence, and then give the variable an address that we can use to look up the sentence later.
In real life mailboxes have to have PO Box numbers but in JavaScript you usually just use lowercase letters or numbers without any spaces.

```
coffee> dogSentence = 'Dogs are the bane of my existence.'
'Dogs are the bane of my existence.'
```


The `=` means *store the thing on the right-hand side in the thing on the left-hand side*.

If you simply type a variable name into the shell, it will print out the value stored in that variable.

```
coffee> dogSentence
'Dogs are the bane of my existence.'
```

### <a id="functions" href="#functions">#</a> Functions

Now that we have our sentence stored in a variable let's give that variable to something that will replace words!
We call things that perform actions like this **functions** because, well, they serve a specific *function* (AKA purpose or action) for us.
Calling them "actions" sounded weird I guess so they went with the word "function" instead.

CoffeeScript has a function called `replace` that does exactly what we want! Functions take in any number of values (zero, one or many) and return either one value or nothing (`undefined`).
The `replace` function is available to use on any strings and takes in two values: the characters to take out and the characters to swap in.
It gets confusing to describe these things so here is a visual example:

```
coffee> dogSentence.replace('Dogs', 'Those blasted dogs')
'Those blasted dogs are the bane of my existence.'
coffee> dogSentence
'Dogs are the bane of my existence.'
```

Notice how the value of `dogSentence` is the same even after we run replace on it? 
This is because `replace` (and most CoffeeScript functions for that matter) it takes the variable or value that we give it and returns a **new value** instead of modifying the thing we passed in.
Since we didn't store the new variable (there is no `=` on the left side of the replace function) it just printed out the return value in our console.


### <a id="standard-library" href="#standard-library">#</a> The "standard library"

You might be wondering what other functions are available in CoffeeScript.
The answer: all JavaScript's.
There are lots **built in, standard libraries** that you can learn about at MDN (A site run by Mozilla that has lotsa nifty information about web technologies).
For example [here is the MDN page on JavaScript's Math object](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Math).

### <a id="third-party-javascript" href="#third-party-javascript">#</a> Third-party JavaScript

There is also a lot of CoffeeScript code available that is **not built in**.
CoffeeScript from third parties is usually referred to as a "library" or "package".
And CoffeeScript can use all JavaScript packages.
You can use `npm` to install packages.
This only works in the installation on your local machine, not the online REPL.

For example, install my favorite package `lodash`, type this in your terminal:

```
npm install lodash
```

Then you can load it under the CoffeeScript shell:

```
coffee> _ = require "lodash"
```

It will print out all the functions `lodash` provides.

Note that `_ = require "lodash"` is not black magic.
First, in CoffeeScript, when calling a function, you can omit the paratheses.
Thus `require "lodash"` is equivalent to `require("lodash")`.
We use `require` function to load a package, and give it a name (`_`).

`lodash` gives you a ton of helpful functions to play with. We'll learn more about how to use them later.

```
coffee> _.first("hello")
'h'
```


### <a id="writing-functions" href="#writing-functions">#</a> Making new functions

You aren't limited to using other peoples functions &mdash; you can also write them yourself.
It's pretty easy!
Let's make a function called `makeMoreExciting` that adds a bunch of exclamation points to the end of a string.

```coffee
makeMoreExciting = (string) -> string + '!!!!'
```

In my head I read it out loud like this: "there's a function takes in a string and returns a new copy of that string that has a bunch of exclamation points at the end, and we assign a name to it `makeMoreExciting`".


Let's use our function:

```
coffee> makeMoreExciting('louning')
'louning!!!!'
```

You could also call the same function by passing in a variable that points to a string (in the above example we just typed the string straight in there as a value instead of saving it to a variable first):

```
coffee> sentence = "time for a nap"
coffee> makeMoreExciting(sentence)
'time for a nap!!!!'
```

The line `makeMoreExciting(sentence)` is equivalent to saying `sentence + '!!!!'`.
What if we wanted to **modify in-place** (aka update) the value of sentence? Simply save the return value of the function back into our `sentence` variable:

```coffee
> sentence = makeMoreExciting(sentence)
'time for a nap!!!!'
coffee> sentence
'time for a nap!!!!'
```

Now `sentence` will have the exclamation marks in it!

### <a id="loops" href="#loops">#</a> Loops

Now that we have some basic skills under our belt, (*Author's note: do cats even wear belts?*) we can start being lazy. 
What?!
Yes, that's right: programming is about being lazy.
Larry Wall, inventor of the Perl programming language, called laziness the [most important virtue](http://c2.com/cgi/wiki?LazinessImpatienceHubris) of a good programmer.
If computers didn't exist you would have to do all sorts of tedious tasks by hand, but if you learn to program you can lay in the sun all day while a computer somewhere runs your programs for you.
It is a glorious lifestyle filled with relaxation!

Loop in CoffeeScript is simple.

Suppose we have a function than prints the number:
```
coffee> logANumber = (someNumber) -> console.log(someNumber)
```

We can apply it to numbers from 1 to 10:

```
coffee> logANumber(num) for num in [1..10]
1
2
3
4
5
6
7
8
9
10
```

If we were to manually write out what the above code is doing in the above code it would look like this:

```coffee
logANumber(0)
logANumber(1)
logANumber(2)
logANumber(3)
logANumber(4)
logANumber(5)
logANumber(6)
logANumber(7)
logANumber(8)
logANumber(9)
```

But cats refuse to do unnecessary manual work like this so we must always ask ourselves, *"am I doing this in the laziest way possible?"*.


### <a id="lists" href="#lists">#</a> Lists

Imagine you need to keep track of all your buddies.
Well, a list will do just fine.
Think of a list like a sorted list that you can keep *tons* of stuff in.

This is how you make one:

```coffee
myCatFriends = ["tommy", "tabby", "ceiling"]
```

Sweet! Now you have a list of your cat buddies.

Elements (that is what you call a single item in a list) that are stored within lists start at 0 and count up from there.
So `myCatFriends[0]` returns `tommy` and `myCatFriends[1]` returns `tabby`... etc etc.


If you made a brand new cat friend at the hippest cat club the other night and you want to add them to your list it is super simple:

```coffee
coffee>myCatFriends.push("super hip cat")
4
```

To check that the new cat made it into your list you can use `.length`:

```
coffee> myCatFriends.length
4
```


Notice how `push` returned the length?
Handy!
Also take note that lists will always **preserve ordering** which means they will remember the order in which you added or defined things.
Not everything in CoffeeScript preserves ordering so remember this special property of lists!

### <a id="objects" href="#objects">#</a> Objects

Lists are good for lists, but for other tasks they can be hard to work with. Consider our list of cat friends.
What if you also wanted to store more than just names?

```coffee
myCatFriends = ["tommy", "tabby", "ceiling"]
lastNames = [
  "the cat",
  "cat",
  "cat",
]
addresses = [
  "The Alley"
  "Grandmas House"
  "Attic"
]
```

Note that lists can be multiple lines (need indention) and we can omit the comma.

Sometimes it is nice to have all of the addresses or names in one variable. But sometimes you have a cat in mind, let's say Tommy, and you just want to look up that cat's address.
With lists it takes a lot of work because you can't just say 'hey list, give me Tommy's address' because 'Tommy' is in one list and his address is in a totally different list.

```coffee
tommysPosition = 0
console.log(myCatFriends[tommysPosition], addresses[tommysPosition])
```


This can be brittle because if our lists change and we add a new cat to the beginning we would have to also update our `tommysPosition` variable to point to the new location of Tommy's information in the lists!
Here is a easier to maintain way to store information like this using objects:

```coffee
firstCat = { name: "tommy", lastName: "the cat", address: "The Alley" }
secondCat = {
  name: "tabby",
  lastName: "cat",
  address: "Grandmas House",
}
thirdCat =
  name: "ceiling"
  lastName: "cat"
  address: "Attic"
```

Again, we can write multiline objects (need indention) and omit `{`, `}` and `,`.
Why would we do it this way?
Because now we have a variable for each cat that we can use to get that cats values in a more convenient and readable way. 

```coffee
coffee> console.log(firstCat.name, firstCat.address)
tommy The Alley
coffee> console.log(firstCat.["name"], firstCat.["address"])
tommy The Alley
```

`object.string` is a shortcut for `object["name"]`.

You can think of Objects like keys on a keyring.
Each one is for a specific door and if you have nice labels on your keys you can open doors very fast.
In fact, the things on the left hand side of the `:` are called **keys** (are also known as **properties**) and the things on the right hand side are **values**.

```coffee
# an object with a single key 'name' and single value 'tommy'
{ name: 'tommy' }
# or
name: 'tommy'
```

So why would you ever use lists if you can just put your data in objects? Because objects don't remember the order of the keys that you set.
You might enter in an object like this:

```coffee
{ date: "10/20/2012", diary: "slept a bit today", name: "Charles" }
```

But the computer could give it back to you like this:

```coffee
{ diary: "slept a bit today", name: "Charles", date: "10/20/2012" }
```

Or like this!

```coffee
{ name: "Charles", diary: "slept a bit today", date: "10/20/2012" }
```

So you can't ever trust the order of keys in objects.

If you wanna get REALLY fancy you can make an list filled with objects, or an object filled with lists!

```coffee
moodLog = [
  {
    date: "10/20/2012",
    mood: "catnipped"
  }, 
  {
    date: "10/21/2012",
    mood: "nonplussed"
  },
  {
    date: "10/22/2012",
    mood: "purring"
  }
]


# ordered from least to most favorite
var favorites = {
  treats: ["bird sighting", "belly rub", "catnip"],
  napSpots: ["couch", "planter box", "human face"]
}
```

When you combine different things like this you are making **data structures**, just like legos!

Lists and objects can be considered equvilent though.
For example, list can be considered as a shortcut of object, we just use natural numbers as keys.

```
coffee> thisIsAList = ['a', 'b', 'c']
[ 'a', 'b', 'c' ]
coffee> thisIsNotAList = { 0: 'a', 1: 'b', 2: 'c'}
{ '0': 'a',
  '1': 'b',
  '2': 'c' }
coffee> thisIsAList[0]
'a'
coffee> thisIsNotAList[0]
'a'
coffee> thisIsNotAList[0] is thisIsAList[0]
true
```

And object can be considered as a shortcut of compound list.
We build a compound list contains pairs (lists containing two elemens), and use the first element (`[0]`) as key, the second (`[1]`) as value.

```
coffee> thisIsAnObject = { date: "10/20/2012", diary: "slept a bit today", name: "Charles" }
{ date: '10/20/2012',
  diary: 'slept a bit today',
  name: 'Charles' }
coffee> thisIsNotAnObject = [ ["date", "10/20/2012"], ["diary", "slept a bit today"], ["name", "Charles"] ]
[ [ 'date', '10/20/2012' ],
  [ 'diary', 'slept a bit today' ],
  [ 'name', 'Charles' ] ]
coffee> thisIsAnObject.date
'10/20/2012'
coffee> coffee> thisIsNotAnObject.filter((pair) -> pair[0] is 'date')[0][1]
'10/20/2012'
```

This line needs some explaination:

```coffee
thisIsNotAnObject.filter((pair) -> pair[0] is 'date')[0][1]
```

We use the `filter` function to return a list containing all the pairs whois first element (`[0]`) is `date`.
The `filter` function takes two arguments, the list and a function for filtering.
We use the function `(pair) -> pair[0] is 'date')` without giving it a name.
This is call anonymous function. 
We know there are only one pair, thus we use (`[0]`) to get this pair, then (`[1]`) to get its second element ("value").

Note that use compound list does not forbid duplicate "keys".
And seek all pairs for a "key" is very slow.
Thus it is a bad idea to use it for substitute objects.



### That is the end for now, but here's what I'm working on:

- More crazy looping!
- JSON and TOML.
- Grabbing stuff from other pages on the Internet and displaying it.
- How to use GitHub to find and share code.
- Use CoffeeScript in frontend.
- More Node.js and server side catgramming.

Got another topic you wanna see covered? Open an issue for it [on github](http://github.com/weakish/cs4cats).

I'd recommend coming back again tomorrow and going through the entire thing again from the beginning! It might take a few times through before you get everything (programming is hard). Just try to avoid reading this page in any rooms that contain shiny objects . . . they can be incredibly distracting.

### <a id="recommended-reading" href="#recommended-reading">#</a> Recommended reading

CoffeeScript for cats skips over lots of details that aren't important for getting started (cats are not known for their attention spans), but if you feel like you need to dive in deeper then check these out:

- [CoffeeScript Homepage](http://coffeescript) provides more information about CoffeeScript.
- [NodeSchool.io](http://nodeschool.io/) is a community driven, open source educational software that teaches various node.js and JavaScript skills in an interactive, self-guided format. I helped make NodeSchool! Sadly it features less cats than this page. 
- [Mozilla's JavaScript Guide](https://developer.mozilla.org/en-US/docs/JavaScript/Guide) also has a pretty sweet intro chapter called [values, variables and literals](https://developer.mozilla.org/en-US/docs/JavaScript/Guide/Values,_variables,_and_literals)

[CoffeeScript for cats](http://weakish.github.io/cs4cats) is translated and adapted from [JavaScript for cats (JSForCats.com)](http://jsforcats.com).
[JSForCats.com](http://jsforcats.com) is a labor of love and work in progress by [@maxogden](http://twitter.com/maxogden).

If you would like to contribute and make this tutorial better, you can go to this tutorial's GitHub repo [cs4cats](https://github.com/weakish/cs4cats) or the upstream GitHub repo [javascript-for-casts](http://github.com/maxogden/javascript-for-cats). 