# Multi Languages With JQuery

This project show you how to add multi language your web site project with JQuery.

Firstly add JQuery library in your **head** like below.

```html
<script
src="https://code.jquery.com/jquery-2.2.4.min.js"
integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44="
crossorigin="anonymous"></script>
```

You can use it in your html codes like below.

```html
<h1 name="translate" caption="h1">Hi H1 tag</h1>
```

After adding this script you create a file that name is **translate.js** then write a simple functions to select which language to add.

Add a function that gives you a resources that included translations values.

```javascript
function getLangResources(){
    // Define arrays how many language you want to translate
    var tr = new Array();
    var en = new Array();
    // caption tag name
    tr['hello_world'] = "Merhaba Dünya"; 
    en['hello_world'] = "Hello World";
    
    // Added new array defined arrays.
    var resources = new Array();
    resources['tr'] = tr;
    resources['en'] = en;
    
    return resources;
}
```

Add a function that change your tags and values.
I have used **name** tag and **caption** tag. JQuery **each** method finds all tags and chage it.

```javascript
function changeLanguage(lng){
var resources = getLangResources()[lng];
$("h1[name='translate']").each(function(i, elt){
    $(elt).text(resources[$(elt).attr("caption")]);
});
}
```

When your document is ready you can add your code like below in **document.ready** or **$(function(){})**.

```javascript
$(function() { 
    // Default Language
    changeLanguage("en");
 
    // Tr button click
    $("#tr_button").click(function(){
        changeLanguage("tr");
    });

    //Eng button click
    $("#eng_button").click(function(){
        changeLanguage("en");
    });
});
``` 

Simply change language values with this method.