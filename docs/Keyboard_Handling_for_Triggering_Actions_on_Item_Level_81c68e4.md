<!-- loio81c68e4654994da5935add669e48f20c -->

| loio |
| -----|
| 81c68e4654994da5935add669e48f20c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/81c68e4654994da5935add669e48f20c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/81c68e4654994da5935add669e48f20c)</div>

## Keyboard Handling for Triggering Actions on Item Level

The following keys and key combinations are used for triggering events of clickable elements.


<table>
<tr>
<th>

Key combination



</th>
<th>

Behavior



</th>
</tr>
<tr>
<td>

[Spacebar\]



</td>
<td>

If items are **not selectable** and focus is on an item, trigger the item event.

> ### Tip:  
> If you press and hold the key, you can cancel the trigger action by pressing [Shift\].

If items are selectable, select/deselect the item.



</td>
</tr>
<tr>
<td>

[Enter\]



</td>
<td>

If focus is on an item, trigger the item event immediately after the key press.



</td>
</tr>
</table>

***

Use the following keys to trigger additional actions \(if supported\):


<table>
<tr>
<th>

Key combination



</th>
<th>

Behavior



</th>
</tr>
<tr>
<td>

[Delete\]



</td>
<td>

If deletion of items supported:

If focus is on an item, delete the item. Move focus to the next item.

If the deleted item is the last item, move focus to the previous item.

If the deleted item is the last remaining item, move focus to the next control in the tab order.



</td>
</tr>
<tr>
<td>

[F2\]



</td>
<td>

If *Detail* of items is supported:

If focus is on an item, trigger the click event for the *Detail* button.



</td>
</tr>
</table>

