---
title: Installation Guide
onpagelink: installation
weight: 2

---
### **Installation Instructions**

Copy the following code into theblock of your webpage:

    
    
  

    <!-- dependencies (jquery, handlebars and bootstrap) -->
      <script type="text/javascript" src="//code.jquery.com/jquery-1.11.1.min.js"></script>
      <script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.5/handlebars.min.js"></script>
      <link type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css" rel="stylesheet"/>
      <script type="text/javascript" src="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/js/bootstrap.min.js"></script>
      <!-- alpaca -->
      <link type="text/css" href="//cdn.jsdelivr.net/npm/alpaca@1.5.27/dist/alpaca/bootstrap/alpaca.min.css" rel="stylesheet"/>
      <script type="text/javascript" src="//cdn.jsdelivr.net/npm/alpaca@1.5.27/dist/alpaca/bootstrap/alpaca.min.js"></script>
    

Call $.alpaca() with your form schema and any configuration:

     
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
    

This will generate the following html5 form using Twitter bootstrap and Alpaca combination.
