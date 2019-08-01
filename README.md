# Multi Languages With JQuery

This project show you how to add multi language your web site project with JQuery.

Firstly add JQuery and Bootstrap libraries in your **head** like below.

```html
<!-- Add JQuery lib -->
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" 
integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
crossorigin="anonymous">
</script>

<!-- Add Bootstrap lib -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" 
integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1"
crossorigin="anonymous">
</script>

<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" 
integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" 
crossorigin="anonymous">
</script>	

<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" 
integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" 
crossorigin="anonymous">
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
