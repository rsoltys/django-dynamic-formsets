# django-dynamic-formsets

A lightweight plugin for managing Django formsets with jQuery.


## About this plugin

This [jQuery](http://jquery.com/) plugin helps you create more usable [Django](http://www.djangoproject.com/) formsets by allowing clients to add and remove forms on the client-side.

It was primarily developed by [Stanislaus Madueke](https://github.com/elo80ka), and re-packaged as a static Django app (with a couple shiny new enhancements and more docs) by [The Dallas Morning News](https://github.com/DallasMorningNews/).

This version of this plugin (like its predecessor) is available under the [BSD License]().

****


## Getting started

1.   Download this repo or install from PyPI:

    ```bash
    pip install django-dynamic-formsets
    ```

2.   Then add `dynamic_formsets` to your `INSTALLED_APPS` setting and run `python manage.py collectstatic`.

3.   You can now make your formsets dynamic by adding the following lines to a template:

    ```Django
    {% load static %}

    ...

    {% comment %}
        (Your templated DOM here, possibly something like this:)
    {% endcomment %}

    <form id="my-form" method="post" action="">
        {% csrf_token %}
        {{ formset.media }}
        {% for form in formset %}
            <div class="individual-form">
                {{ form.as_p }}
            </div>
        {% endfor %}
    </form>

    ...

    <script src="{% static "dynamic_formsets/jquery.formset.js" %}" type="text/javascript"> </script>

    <script type="text/javascript">
        $('.individual-form').formset();
    </script>
    ```

****


## Configuration

Once you've followed steps 1 to 3 above, you're ready to customize the formset-handling javascript that's now on your page.

Detailed information about all the settings you can change in the javascript will be added to this repo very soon.
