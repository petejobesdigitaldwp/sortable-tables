# sortable-tables

The script converts simple HTML data tables into sortable tables. It adds the necessary interactive elements, functionality and accessibility, ensuring that the table degrades gracefully if it needs to.

## Creating a sortable table

1. Create a simple HTML data table.
2. Put `class="sortable"` on the ```<table>``` element.
3. Put `class="sortable-colum"` on each ```<th>``` element.
4. Inside each ```<th>``` element, put ```<span class="th-content">Column name</span>```.
5. Inside each ```<span class="th-content">``` put ```<i class="arrow!"</i>```.

```
<table class="sortable">
<thead>
<tr>
<th class="sortable-colum">
<span class="th-content">Column title <i class="arrow"></i></span>
</th>
...
</tr>
</thead>
...
</table>
```

6. Use the `data-sortby` attribute on any ```<th class="sortable-column">``` to be sorted. Choose from `numeric`, `date`, `text`, or `money`. If the `data-sortby` attribute is not present, the script defaults to `numeric` as the sort criterion.



7. Call the `sortable-table.js` script from the end of the document.
```
<script src="sortable-table.js"></script>
</body>
</html>
```

### What happens next

The script:

* Sets `aria-sort="none"` to each ```<th class="sortable-column">``` element.
* Adds a `click` event listener to each ```<th class="sortable-column">``` element.
* Sets `role="button"` and `tabindex="0"` to each ```<span class="th-content">``` element.
* Adds a `keydown` event listener to each ```<span class="th-content">``` element, that listens for the space (keycode 13) and enter (keycode 32) keys.
* Uses the `data-sortby` attribute to determine the sort criteria and sorts each column accordingly.
* Sets the `aria-sort` attribute to `ascending` or `descending` as appropriate.
* Updates the ```<i class="arrow">` element with the appropriate visual marker for the sort order.
