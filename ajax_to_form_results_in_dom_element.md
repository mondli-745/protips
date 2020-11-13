### How to add Ajax functionality to a form for replacing a DOM element with a partial?

Add to form `remote: true` or refactor to [form_with](https://apidock.com/rails/ActionView/Helpers/FormHelper/form_with)

In your controller action, e.g. foobar, add:

```
def foobar

  respond_to do | format |
    format.js
    format.html
  end

end
```

Create the same file name as the controller action:

`foobar.js.erb`

Content of `foobar.js.erb`:

`$("#id").replaceWith("<%= j render(‘partial_name’) %>");`

Perhaps possible to extract partial from current view

`_partial_name.html.erb`

Add this back in the view with

`<%= render "partial_name" %>`

Done.
