# "More" Remover Scriptlet for Gmail

A Tampermonkey script to remove the "More" buttons from the labels sidebar in Gmail.

## Description

It removes the two "More" buttons to free up some space and to avoid accidentally expanding the top "More" when dragging an email over it towards the bottom labels list.

*Before* and *After* images:

<p float="left">
  <img src="https://i.imgur.com/IxTrGmn.png" width="200" style="margin-right: 10px;" />   
  <img src="https://i.imgur.com/yESFWVD.png" width="200" /> 
</p>

## Usage

The script is most useful with all commonly used labels being ticked to Show in the label options. It makes the label lists fixed instead of constantly changing size.

### Creating the scriptlet:

1. Get Tampermonkey.
2. In Tampermonkey select "Create new script..."
3. Overwrite the contents of the new script with the following code:

```js
// ==UserScript==
// @name         Gmail More Hider
// @version      1
// @description  Hide the two "More" label buttons to stop them automatically expanding
// @grant        none
// @match    https://mail.google.com/mail/u/0/*
// ==/UserScript==

function hideElements() {
  document.querySelectorAll('div.n6').forEach(element => {
    element.style.display = 'none';
  });
}

// Run the function initially
hideElements();

// Re-run the function every time the page content is updated
new MutationObserver(hideElements).observe(document, { childList: true, subtree: true });
```

### Using the scriptlet to remove "More" labels/buttons in Gmail:

1. Enable the script in Tampermonkey.
2. Navigate to gmail, e.g. https://mail.google.com/mail/u/0/#inbox

### Restoring removed labels/buttons:

1. Disable the script in Tampermonkey.
2. Refresh the page or navigate away and back to it.

## License

[MIT](https://choosealicense.com/licenses/mit/)