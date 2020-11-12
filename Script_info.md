* [onRowSelected Example](#onRowSelected-Example)
* [Star Rating Filter Example](#Star-Rating-Filter)


<br/><br/><br/><br/>
## onRowSelected Example
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
<br/><br/><br/><br/>
## Star Rating Filter
```html
<div class="btn-group">
    <button class="grid-function-link dropdown-toggle" type="button" id="rating-dropdown" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Ratings
    </button>
    <div class="dropdown-menu" aria-labelledby="rating-dropdown">
        <div class="dropdown-item rating-filter-item">
            <label for="stars_5">
                <input type="checkbox" id="stars_5" name="filter-by-rating" checked />
                <div class="rating-cell">
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                </div>
            </label>
        </div>
        <div class="dropdown-item rating-filter-item">
            <label for="stars_4">
                <input type="checkbox" id="stars_4" name="filter-by-rating" checked />
                <div class="rating-cell">
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fal fa-star"></i></span>
                </div>
            </label>
        </div>
        <div class="dropdown-item rating-filter-item">
            <label for="stars_3">
                <input type="checkbox" id="stars_3" name="filter-by-rating" checked />
                <div class="rating-cell">
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fas fa-star"></i></span>
                    <span><i class="fal fa-star"></i></span>
                    <span><i class="fal fa-star"></i></span>
                </div>
            </label>
         </div>
         <div class="dropdown-item rating-filter-item">
             <label for="stars_2">
                 <input type="checkbox" id="stars_2" name="filter-by-rating" checked />
                 <div class="rating-cell">
                     <span><i class="fas fa-star"></i></span>
                     <span><i class="fas fa-star"></i></span>
                     <span><i class="fal fa-star"></i></span>
                     <span><i class="fal fa-star"></i></span>
                     <span><i class="fal fa-star"></i></span>
                 </div>
             </label>
         </div>
         <div class="dropdown-item rating-filter-item">
                <label for="stars_1">
                 <input type="checkbox" id="stars_1" name="filter-by-rating" checked />
                    <div class="rating-cell">
                        <span><i class="fas fa-star"></i></span>
                        <span><i class="fal fa-star"></i></span>
                        <span><i class="fal fa-star"></i></span>
                        <span><i class="fal fa-star"></i></span>
                        <span><i class="fal fa-star"></i></span>
                    </div>
                </label>
         </div>
   </div>
</div>
```

```javascript
 var filterArrays = [
     "node.data.overall_rating == 5",
     "node.data.overall_rating == 4",
     "node.data.overall_rating == 3",
     "node.data.overall_rating == 2",
     "node.data.overall_rating == 1",
 ];
 
  $('.rating-filter-item input').on('change', function (e) {
     var rating_id = $(this).attr("id"),
         rating_count = parseInt(rating_id.substring(rating_id.length - 1, rating_id.length));

     if ($(this).is(":checked")) {
             filterArrays.push("node.data.overall_rating == " + rating_count);
     } else {
         filterArrays = filterArrays.filter(item => item !== "node.data.overall_rating == " + rating_count);
     }

     externalFilterChanged(filterArrays);
 })
```
