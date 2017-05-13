# Sngine automatic group and page url generator

### 1º Add the .js (upload the "js" folder) to your theme folder

The folder and its contents have this structure

-> js (folder)
--> stringtourl (folder)
---> jquery.slugify.js (.js file)

### 2º Edit the _js_files.tpl

Go to line 131 and add one below, copy and paste this code (_REMEMEBER TO CHANGE YOUR THEME FOLDER NAME IN THE CODE)

```js
<script src="{$system['system_url']}/content/themes/YOURTHEMEFOLDERNAME/js/stringtoslug/jquery.slugify.js" type="text/javascript"></script>
```

### 3º Add the rest of the code in the forms

You must add this code below each form to create or edit a group or page, in index.tpl, in group.tpl and in page.tpl

```js
<script src="{$system['system_url']}/includes/assets/js/jquery/jquery-3.1.1.min.js"></script>
<script type="text/javascript" charset="utf-8">
$().ready(function() {
    $('#username').slugify('#title');
    $('[id=slugresult]').slugify('#title');

    var pigLatin = function(str) {
        return str.replace(/(\w*)([aeiou]\w*)/g, "$2$1ay");
    }

    $('#pig_latin').slugify('#title', {
        slugFunc: function(str, originalFunc) {
            return pigLatin(originalFunc(str));
        }
    });

});
</script>
```

License
----

MIT
