
# QGO Desktop Assessment

## Approach

Status:

1. Add the ability to delete items. - Complete
2. Be able to mark items as complete. And then toggle them back to incomplete. - Complete
3. Add a filter than can be toggled to hide completed items. - Complete


### Some small tweaks

The first thing I noticed when running this was that new todo items couldn't be added by hitting return while focused on the input. I had to tab over to the input button to add them. This didn't seem ideal for accessibility so I wrapped the `ItemCreator` elements in a form and created a new `save` function that could handle the `onSubmit` event from the form and also the `onClick` event from the button.

### Delete and toggle

Adding the delete and toggle features were quite straight forward. I added an action for removing an item that took an item id which the reducer could then filter on to remove the chosen item from state. Toggling is similar but I also added a property to each item object to define its status, the action takes an id and the reducer maps the items and toggles the chosen one.

On the UI side of this I added an aria label to the toggle checkbox that can inform users using screen readers what the checkbox will do in relation to an items status.

### Filtering

For speed I based the filtering on a single object that would hold a key. This lead to some hard coding of the filter on the UI side that isn't ideal but could be refactored without too much difficulty.

### Testing

Could have written more tests but didn't want to overrun on time. 
On the UI side, I added tests for removing and toggling items, and also filtering. On the state side, I created tests for the filter option action and the remove and toggle item actions.

### Expanding

Areas for expansion would be more tests, better styling and possibly a different approach to styling such as styled components. More lint rules and possibly a library for maintaining immutability of state such as seamless-immutable.
