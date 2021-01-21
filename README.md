# TQUENS CSS RULE SETS

## Tag Cell Example

```html
<main>
    <div class="test-block">
        <div class="test-block-item">
            <div class="test-block-content" id="tags">
                <div class="tag-cell">

                </div>
            </div>
        </div>
    </div>
</main>
```

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
main {
    min-height: 100vh;
}
.test-block {
    height: 100vh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}
.test-block .test-block-item {
    /* width: 400px; */
    height: 500px;
}
.test-block .test-block-item .test-block-content {

}

.tag-cell {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-around;
    height: 20px;
}
.tag-cell .tag-item {
    width: 10px;
    height: 15px;
}
```

```javascript
var tag_data = [
    {
        name: "Tag 1",
        color: "red"
    },
    {
        name: "Tag 2",
        color: "green"
    },
    {
        name: "Tag 3",
        color: "blue"
    }
];

$(document).ready(function() {
    tag_data.map(item => {
        var tag_item = document.createElement('span');

        tag_item.className = "tag-item";
        tag_item.setAttribute("data-toggle", "tooltip");
        tag_item.setAttribute("data-placement", "bottom");
        tag_item.setAttribute("title", item.name);
        tag_item.style.backgroundColor = item.color;

        $(tag_item).tooltip();

        document.querySelector('.tag-cell').appendChild(tag_item);
    })
})
```
