# specification

## Text output

Print text 

```
print This text will be printed.
print This text will be the same line.
```

`p` is alias for `print`.
Commands `print Some text` and `p Some text` are equivalent.

Print text with new line

```
println This text will be printed.
println This text will be on separate line.
```

`pln` is alias for `println`.
Commands `println Some text` and `pln Some text` are equivalent.

## Labels

Labels is used to describe location or procedures.

```
:label
/*
 There must be some operators
 */ 
end
```

## End operator

`end` operator marks label end and pass control to player.

## Common label

`common` is a special label that will be called on each `goto` and `btn` call.

You can redefine common name via `common` system variable.
If `common` variable is set label `common_{value}` will be called on each `goto` and `btn` call.

## Links

Links is a fast way to create 

`[[link]]` link to label 'link' in text

`[[link name | label_name ]]`  link to label_name

`[[link name | ...operators... ]]`  link to call operators


## Buttons

Buttons are similar to links but are displayed after the text and not in it.

```
btn label_name
```

button redirects to label `label_name` and has text "label_name".

```
btn label_name, Button text
```

button redirects to label `label_name` and has text "Button text".

```
btn operator1 & operator2 & ...
```

button will call operator1 and operator2 and ... on click and has text ???

```
btn operator1 & operator2 & ..., Button text
```

button will call operators and has text "Button text"

## User input

```
input var
```

will wait for user input and store it in variable `var`.
Can be used to ask players name or to create quests with input.

```
anykey
```

will wait for any key press.

```
anykey var
```

will wait for any key press and store pressde key in `var`.


## Procedure

```
proc label
```

will go to label, execute operators until `end` and then return to the operator after `proc` call.

forget_proc (?)


## Variables

Set variable

```
apples = 4
```

Variable substitution

```
pln I have #apples$ apples.
```

## Special characters

```
##{code}$ 
```

## Sound

Play music file once

```
play "file_name"
```

## Comments 

URQ use C-style comments

```
/*
  This is comment
*/
```

## Inventory

Inventory is a list of variables available for player.


Add items to inventory:
```
inv+ Item
``` 

will add one Item to inventory.

```
inv+ X, Item
```

will add X Items to inventory

Remove items fro inventory:

```
inv- Item
```

will remove one Item from inventory.

```
inv- X, Item
```

will remove X Items from inventory.

Set count of Item to zero

```
invkill Item
```

will set count of Item to 0.

```
invkill
```
will delete all inventory.


## Conditional 

if condition then operators_true else operators_false

Goto

goto label - go to label


## Random number generation

```
rnd
```

will return float value in interval 0 - 1 (exclusive)

```
rndX
``` 

will return integer value in interval 1 - X (inclusive)


## Pause

```
pause {ms_count}
```

will pause game for `ms_count` milliseconds.
It can be used to simulate waiting but it is strongly recommended not to use values greater than 5 000 milliseconds.



quit - termination of quest

save - save game state to slot


MAth operations

() 

not

*, /, +, -,

<, <=, >, >=,
= equals
== string equlas with mask  * and ? glob

!=, <> - not equals
&& and - and
|| or - or


## Sysytem varianbles

### count

```
count_{label}
```

stores each label visit count.

### music

```
music = "realtive/path/to/file.mp3"
``` 

will play file as background music.


common

called on each goto operations

### current_loc

`current_loc` 

read only.
Stores current location.

### previous_loc

`previous_loc `

read only.
Stores previous location.

### Text color

`style_dos_textcolor` 

set dos compatible color as int in range [0, 15].

`style_textcolor`

set textcolor in hex format.

`style_backcolor`

set background color in hex foramt.

image - show image



time - return seconds from midnight
