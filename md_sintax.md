I took all these info from [this website](https://confluence.atlassian.com/display/STASH/Markdown+syntax+guide)

************************************************************************
# This is an H1
## This is an H2
###### This is an H6

###I need a picture

![alt tag](https://raw.githubusercontent.com/GiuseppeFasanella/Git_commands/master/images/basso.png)

Each paragraph begins on a new line. Simply press <return> for a new line.
 
For example, 
like this.
 
You'll need an empty line between a paragraph and any following markdown construct, 
such as an ordered or unordered list, for that to be rendered. Like this:
 
* Item 1
* Item 2

*Italic characters*
_Italic characters_
**bold characters**
__bold characters__
~~strikethrough text~~

* Item 1
* Item 2
* Item 3
    * Item 3a
    * Item 3b
    * Item 3c

1. Step 1
2. Step 2
3. Step 3
    a. Step 3a
    b. Step 3b
    c. Step 3c

1. Step 1
2. Step 2
3. Step 3
    * Item 3a
    * Item 3b
    * Item 3c

Introducing my quote:
  
> Neque porro quisquam est qui
> dolorem ipsum quia dolor sit amet,
> consectetur, adipisci velit...

Use the backtick to refer to a `function()`.
  
There is a literal ``backtick (`)`` here.

Indent every line of the block by at least 4 spaces or 1 tab. 
 
This is a normal paragraph:
  
    This is a code block.
    With multiple lines.
 
Alternatively, you can use 3 backtick quote marks before and after the block, like this:
 
```
This is a code block
```
 
To add syntax highlighting to a code block, add the name of the language immediately
after the backticks: 
  
```javascript
var oldUnload = window.onbeforeunload;
window.onbeforeunload = function() {
    saveCoverage();
    if (oldUnload) {
        return oldUnload.apply(this, arguments);
    }
};
```

This is [an example](http://www.slate.com/ "Title") inline link.
 
[This link](http://example.net/) has no title attribute.

| Day     | Meal    | Price |
| --------|---------|-------|
| Monday  | pasta   | $6    |
| Tuesday | chicken | $8    |

