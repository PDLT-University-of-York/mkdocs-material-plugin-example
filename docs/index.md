# Mkdocs Klipse example

## Test of executable code


In this Mkdocs sample we're using the [klipse plug-in](https://github.com/viebel/klipse) to make some of the python code editable. There are two examples below. If you edit the code values, the output will change.

### Example 1


<div class="language-klipse-python">

```eval-python
def factorial(n):                                   
  if n == 0:                          
    return 1                              
  else:
    return n * factorial(n - 1)           

print(factorial(5))
```
</div>

### Example 2

<div class="language-klipse-python">
number_1 = 4
number_2 = 7

# set the variable, total, to the sum of the values stored in these two variables
total = number_1 + number_2

print(total)
</div>

## How to use

To enable Klipse, the overrides folder needs to be enabled in the theme section of the mkdocs.yml. 

``` yml

theme:
  name: material
  custom_dir: overrides

```

The custom ```main.html``` file in that folder, as shown in this repository, then adds the necessary files to the standard html template:

``` html
{% extends "base.html" %}


{% block styles %}
	{{ super() }}
	    <link rel="stylesheet" type="text/css" href="https://storage.googleapis.com/app.klipse.tech/css/codemirror.css">
		<script>
		    window.klipse_settings = {
		        selector_eval_python_client: '.language-klipse-python', // css selector for the html elements you want to klipsify
		    };
		</script>
{% endblock %}

{% block scripts %}
	{{ super() }}
	    <script src="https://storage.googleapis.com/app.klipse.tech/plugin_prod/js/klipse_plugin.min.js"></script>
{% endblock %}
```

Within the markdown, any code that needs to be executable should then be wrapped using the div tags shown here:


``` html
<div class="language-klipse-python">
	number_1 = 4
	number_2 = 7

	# set the variable, total, to the sum of the values stored in these two variables
	total = number_1 + number_2

	print(total)
</div>
```

