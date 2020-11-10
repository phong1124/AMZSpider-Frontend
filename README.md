# AMZSpider Frontend

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