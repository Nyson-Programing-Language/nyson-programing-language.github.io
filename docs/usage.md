# How to use
in a terminal type
```
nyson test.nys
```
you might have to change the word nyson to your nyson file location and change test.nys to any file you want that has the .nys ending

## Print/Log
To print strings in Nyson, simply use the log() function. The log() function can merge vars, ints, and strs innto a single line of text.
```
log("hello world");
```
Merging strs and vars requires adding a space between the two paramters, as so:
```
dec str world : "world";

log("hello" world)
```
log() can concatenate ints and strs into text, and will give no resulting errors even when an int variable is not converted to a str type.
```
dec int age : 14;

log("I am " age " years old!"
```

## Math
The math function allows for powerful operations and can be used in other built in functions such as log(); math can also be used in variables to declare values.
```
log(math(5+5));

dec int age_2 = math(10+4);
```

## Loop
```
loop(5) {
    log("loops");
}
```

## Variables
#### Set
```
dec str hello: "bob";
```
this makes a string variable called hello set to bob

#### Call
```
dec str name: "bob";
log("Hello, " name);
```

#### Anonymous variables
```
dec anon: "bob";
log("Hello, " bob);
```
#### Edit variables
```
dec str name: "bob";
log("Hello, " name);
name: "billy";
log("wait your name is, " name);
```


## Random Number
#### Print Random Number
```
log(math(random));
```
this will give you a float between 0 and 1

#### Print Random Number Between 0 and 10

```
log(math(random*10));
```
get something like 5.5539

#### Print Rounded Random Number
```
log(round(math(random*10)));
```
get something like 3

## Functions
#### Without Variables
```
func(sayHello()) {
    log("hello");
}
sayHello();
```

#### With Variables
```
dec str name: "bob";
func(sayHello(names)) {
    log("hello " names);
}
sayHello(name);
```

## If Statements
```
dec str condition : "true";
if (condition == "true") {
    log("true");
}
```

```
if ("1" >= "1") {
    log("true");
}
```

## Sleep
```
log("Hi");
sleep(5000);
log("I was sent 5 seconds later");
```

## Replace
```
log(replace("I am really bad", "bad", "good"));
```
will give "I am really good"

## Trim
```
log(trim("        Hello      "));
```
will give "Hello"

## Import
### File
FILE: hello.nys
```
func(sayhello()) {
    log("hello")
}
```
FILE: main.nys
```
imp("hello.nys")
sayhello()
```
Returns: hello

### Url
```
imp("https://raw.githubusercontent.com/Nyson-Programing-Language/nyson-programming-language/main/examples/Loading%20Bar.nys");
```
plays a loading bar

## Read Files
```
log(getcont("bob.nys"));
```
will give the content of bob.nys

## Set Files
```
setcont("bob.nys", "Hello I am bob.");
```
bob.nys now has "Hello I am bob." as its contents

## Exec
#### Without Output
```
exec("/usr/bin/touch jimmy.nys");
```

#### With Output
```
log(exec("ls -a"));
```

## Input
```
log("What is your name?");
dec str name: input();
log("Hello, " name);
```

## Request
### GET
```
dec str code: request("GET", "https://www.rust-lang.org/");
log("Rust Website code: " code);
```

### POST
```
request("POST", "https://amtitan.free.beeceptor.com", "bob the builder");
```
this sends "bob the builder" to beeceptor

### Headers
```
request("POST", "https://amtitan.free.beeceptor.com", "{\"name\":\"nyson\"}", "Content-Type: application/json");
```
this sends '{"name":"nyson"}' to beeceptor with the header of content-type equal to application/json

## Music
```
use audio;
audio("doom.mp3");
sleep(9325);
log("DROP");
```
Playes a file but it dose not wait for the file to end to continue. (this uses cvlc so if you want to change the volume or playing a directory see how to do it in cvlc)

## While loops
```
dec int age: 14;
while(age < "18") {
    log("to young");
    age = math(age+1);
}
```
will say `to young` 4 times

## Exit
```
log("1");
exit();
log("2");
```
will say `1` and not the 2

## Arrays
```
dec arr names : ["neal", "nick", "arthur"];
```
It can also be declare as so:
```
dec arr names : "neal", "nick", "arthur;
```

### Accesing Array Indexes
```
log(names(1));
```

### Append and Cutting
```
// cutting
cut(names, 1);
//appending
append(names, "lucy");
```
## OS

### Get Operating System
```
use os;
log(os());
```
will return one of these


    linux
    macos
    ios
    freebsd
    dragonfly
    netbsd
    openbsd
    solaris
    android
    windows

### Get Total Ram

```
use os;
log(os.total_memory());
```

well return the total amount of ram in kb

### Get Used Ram

```
use os;
log(os.used_memory());
```

well return the ammount of ram used in kb

### Get Total Swap

```
use os;
log(os.total_swap());
```

well return the total ammount of swap in kb


### Get Used Swap

```
use os;
log(os.used_swap());
```

well return the ammount of swap used in kb

## Args

you can do `arg(0)` this will return the first arg (will be the nyson)

## First
```
log(first(["bob", "the", "builder"]));
```
this will print bob

## Last
```
log(last(["bob", "the", "builder"]));
```
this will print builder

## Length
```
log(length(["bob", "the", "builder"]));
```
this will print 3

## Split
```
log(last(split("hi, how are you?", ",")));
```
this will print ` how are you?`

## Split Keep
```
dec arr splitz = splitK("hi, how are you?", ",");
log(splitz(2));
```
this will print `,`

## Time

### System Time
```
log(time());
```
this will return the system time in a unix timestamp

### Internet Time
```
log(internet_time());
```
this will return the time from `time.nist.gov:13`

### Human Readable Time
```
log(timeh("", time()));
```
this will return `52years 1month 13days 7h 9m 39s 145ms`

```
log(timeh("true", "%Y-%m-%d %H:%M:%S.%f"));
```
this will return `2022-02-13 17:43:15.145000000`

## Color

```
use term;
log(red "this will be red!");
```
you can also use multiple things at once
```
use term;
log(red blinking "this will be red and also blinking!");
```
### All the different types are:
- reset
- bold
- dim
- italic
- underline
- blinking
- reverse
- invisible
- strikethrough
- black
- red
- green
- yellow
- blue
- magenta
- cyan
- white
- default
- background_black
- background_red
- background_green
- background_yellow
- background_blue
- background_magenta
- background_cyan
- background_white
- background_default
- bright_black
- bright_red
- bright_green
- bright_yellow
- bright_blue
- bright_magenta
- bright_cyan
- bright_white
- bright_background_black
- bright_background_red
- bright_background_green
- bright_background_yellow
- bright_background_blue
- bright_background_magenta
- bright_background_cyan
- bright_background_white
