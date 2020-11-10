# AMZSpider Frontend Script

## onRowSelected Example
[onRowSelected Example](#onRowSelected-Example)
[another Example](#another)

```html
<button class="grid-function-link dropdown-toggle" type="button" id="action-dropdown" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false" disabled>
    Action on <span data-id="selected-products">0</span> selected
</button>

```

```javascript

var gridOptions = {
    ....
    onRowSelected: onRowSelected,
    ...
}

function onRowSelected(e) {
    var selected_rows = gridOptions.api.getSelectedRows().length;
    $('[data-id="selected-products"]').html(selected_rows);
    if (selected_rows > 0) {
        $('#action-dropdown').removeAttr("disabled");
    } else {
        $('#action-dropdown').attr("disabled", true);
    }
}
```



## another
