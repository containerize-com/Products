---
title: Installation Guide
onpagelink: installation
weight: 2

---

#### **Installation Instructions**

Copy the following code into theblock of your webpage:

 ```


<!-- dependencies (jquery, handlebars and bootstrap) -->
<script type="text/javascript" src="//code.jquery.com/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.5/handlebars.min.js"></script>
<link type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css" rel="stylesheet"/>
<script type="text/javascript" src="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/js/bootstrap.min.js"></script>
<!-- alpaca -->
<link type="text/css" href="//cdn.jsdelivr.net/npm/<span id="cloak551fb97d13442cbce2c47c4913dd3590">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak551fb97d13442cbce2c47c4913dd3590').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy551fb97d13442cbce2c47c4913dd3590='&#97;lp&#97;c&#97;'+'&#64;';addy551fb97d13442cbce2c47c4913dd3590=addy551fb97d13442cbce2c47c4913dd3590+'1'+'&#46;'+'5'+'&#46;'+'27';var addy_text551fb97d13442cbce2c47c4913dd3590='&#97;lp&#97;c&#97;'+'&#64;'+'1'+'&#46;'+'5'+'&#46;'+'27';document.getElementById('cloak551fb97d13442cbce2c47c4913dd3590').innerHTML+='<a '+path+'\''+prefix+':'+addy551fb97d13442cbce2c47c4913dd3590+'\'>'+addy_text551fb97d13442cbce2c47c4913dd3590+'<\/a>';</script>/dist/alpaca/bootstrap/alpaca.min.css" rel="stylesheet"/>
<script type="text/javascript" src="//cdn.jsdelivr.net/npm/<span id="cloak66dd4b6b30a11c0413bdfe93c15a6d1b">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak66dd4b6b30a11c0413bdfe93c15a6d1b').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy66dd4b6b30a11c0413bdfe93c15a6d1b='&#97;lp&#97;c&#97;'+'&#64;';addy66dd4b6b30a11c0413bdfe93c15a6d1b=addy66dd4b6b30a11c0413bdfe93c15a6d1b+'1'+'&#46;'+'5'+'&#46;'+'27';var addy_text66dd4b6b30a11c0413bdfe93c15a6d1b='&#97;lp&#97;c&#97;'+'&#64;'+'1'+'&#46;'+'5'+'&#46;'+'27';document.getElementById('cloak66dd4b6b30a11c0413bdfe93c15a6d1b').innerHTML+='<a '+path+'\''+prefix+':'+addy66dd4b6b30a11c0413bdfe93c15a6d1b+'\'>'+addy_text66dd4b6b30a11c0413bdfe93c15a6d1b+'<\/a>';</script>/dist/alpaca/bootstrap/alpaca.min.js"></script>


```

Call $.alpaca() with your form schema and any configuration:

 ```
 
<div id="form1"></div>
<script type="text/javascript">
$("#form1").alpaca({
    "schema": {
        "title": "What do you think of Alpaca?",
        "type": "object",
        "properties": {
            "name": {
                "type": "string",
                "title": "Name"
            },
            "ranking": {
                "type": "string",
                "title": "Ranking",
                "enum": ['excellent', 'not too shabby', 'alpaca built my hotrod']
            }
        }
    }
});
</script>

```

This will generate the following html5 form using Twitter bootstrap and Alpaca combination.