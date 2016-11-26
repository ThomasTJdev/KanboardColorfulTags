#  COLORFUL TAGS
This will create colorful tags like Gitlab Issue Boards labels.

## TAG property
Add class to the tag rendering in **Kanboard/Template/board/task_footer.php**:
`class="tag-<?= $this->text->e($tag['name']) ?>"`

It should look like this:
```HTML
<?php if (! empty($task['tags'])): ?>
    <div class="task-tags">
        <ul>
        <?php foreach ($task['tags'] as $tag): ?>
            <li class="tag-<?= $this->text->e($tag['name']) ?>"><?= $this->text->e($tag['name']) ?></li>
        <?php endforeach ?>
        </ul>
    </div>
<?php endif ?>
```

## Add CSS style
The style can be added in the UI in the Application Settings.

Change, add or remove the styling below to suit yours tags.

```CSS
.task-tags li {
    border: solid 0.5px grey;
    color: black;
}
[class*="tag-Critical"] {
    background-color: rgb(255, 0, 0);
    border: none!important;
    box-shadow: 0 1px 1px rgba(186, 186, 186, 0.55);
    color: white!important;
}
[class*="tag-Waiting"] {
    background-color: rgb(204, 0, 51);
    border: none!important;
    box-shadow: 0 1px 1px rgba(186, 186, 186, 0.55);
    color: white!important;
}
[class*="tag-Waiting DEV"] {
    background-color: rgb(204, 0, 51);
    border: none!important;
    box-shadow: 0 1px 1px rgba(186, 186, 186, 0.55);
    color: #392727;
}
[class*="tag-Ready"] {
    background-color: rgb(92, 184, 92);
    border: none!important;
    box-shadow: 0 1px 1px rgba(186, 186, 186, 0.55);
    color: #392727;
}
[class*="tag-Call"] {
    background-color: rgb(240, 173, 78);
    border: none!important;
    box-shadow: 0 1px 1px rgba(186, 186, 186, 0.55);
    color: #392727;
}
[class*="tag-Documentation"] {
    background-color: rgb(142, 68, 173);
    border: none!important;
    box-shadow: 0 1px 1px rgba(186, 186, 186, 0.55);
    color: white!important;
}
[class*="tag-Meeting"] {
    background-color: rgb(209, 209, 0);
    border: none!important;
    box-shadow: 0 1px 1px rgba(186, 186, 186, 0.55);
    color: #392727;
}
```
