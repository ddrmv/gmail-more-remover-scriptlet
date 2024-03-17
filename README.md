# "More" Remover Scriptlet for Gmail

A scriptlet to remove the "More" buttons from the labels sidebar in Gmail.

## Description

It removes the two "More" buttons to free up some space and to avoid accidentally expanding the top "More" when dragging an email over it towards the bottom labels list.

*Before* and *After* images:

<p float="left">
  <img src="https://i.imgur.com/IxTrGmn.png" width="200" style="margin-right: 10px;" />   
  <img src="https://i.imgur.com/yESFWVD.png" width="200" /> 
</p>

## Usage

The scriptlet is most useful with all commonly used labels being ticked to Show in the label options.

### Creating the scriptlet:

1. Create a new Bookmark in your browser.
2. In the name field put an appropriate name (e.g. "noMore" or "Gmail More Remover")
3. In the url or location field of the bookmark paste the following code:

```js
javascript: (() => { document.querySelectorAll('div.n6').forEach(element => element.remove()); } )();
```

### Using the scriptlet to remove "More" labels/buttons in Gmail:

1. Navigate to gmail, e.g. https://mail.google.com/mail/u/0/#inbox
2. Use the scriptlet by using the bookmark you created.

### Restoring removed labels/buttons:

1. Refresh the page or navigate away and back to it.

## License

[MIT](https://choosealicense.com/licenses/mit/)