cytoscape-context-menus
================================================================================


## Description

A Cytoscape.js extension to provide context menu around elements and core instance.

![Image of extension](example.png)

## Dependencies

 * Cytoscape.js ^2.7.0


## Usage instructions

Download the library:
 * via npm: `npm install cytoscape-context-menus`,
 * via bower: `bower install cytoscape-context-menus`, or
 * via direct download in the repository (probably from a tag).

`require()` the library as appropriate for your project:

CommonJS:
```js
var cytoscape = require('cytoscape');
var context-menus = require('cytoscape-context-menus');

context-menus( cytoscape ); // register extension
```

AMD:
```js
require(['cytoscape', 'cytoscape-context-menus'], function( cytoscape, context-menus ){
  context-menus( cytoscape ); // register extension
});
```

Plain HTML/JS has the extension registered for you automatically, because no `require()` is needed.

## Default Options
```js
var options = {
    // List of initial menu items
    menuItems: [/*
      {
        id: 'remove', // ID of menu item
        title: 'remove', // Title of menu item
        selector: 'node, edge', // Filters the elements to have this menu item on cxttap
        onClickFunction: function () { // The function to be executed on click
          console.log('remove element');
        },
        disabled: false, // Whether the item will be created as disabled
        hasTrailingDivider: true, // Whether the item will have a trailing divider
        coreAsWell: false // Whether core instance have this item on cxttap
      },
      {
        id: 'hide',
        title: 'hide',
        selector: 'node, edge',
        onClickFunction: function () {
          console.log('hide element');
        },
        disabled: true
      },
      {
        id: 'add-node',
        title: 'add node',
        selector: 'node',
        coreAsWell: true,
        onClickFunction: function () {
          console.log('add node');
        }
      }*/
    ],
    // css classes that menu items will have
    menuItemClasses: [
      // add class names to this list
    ],
    // css classes that context menu will have
    contextMenuClasses: [
      // add class names to this list
    ]
};
```

## API

`cy.contextMenus(options)`
To initialize with options.

`cy.appendMenuItem(item)`
Appends given menu item to the menu items list.

`cy.appendMenuItems(items)`
Appends menu items in the given list to the menu items list.

`cy.removeMenuItem(itemID)`
Removes the menu item with given ID.

`cy.setTrailingDivider(itemID, status)`
Sets whether the menuItem with given ID will have a following divider.

`cy.insertBeforeMenuItem(item, existingItemID)`
Inserts given item before the existingitem.

`cy.moveBeforeOtherMenuItem(itemID, existingItemID)`
Moves the item with given ID before the existingitem.

`cy.disableMenuItem(itemID)`
Disables the menu item with given ID.

`cy.enableMenuItem(itemID)`
Enables the menu item with given ID.

`cy.destroyContextMenus()`
Destroys the extension instance

## Publishing instructions

This project is set up to automatically be published to npm and bower.  To publish:

1. Set the version number environment variable: `export VERSION=1.2.3`
1. Publish: `gulp publish`
1. If publishing to bower for the first time, you'll need to run `bower register cytoscape-context-menus https://github.com/iVis-at-Bilkent/cytoscape.js-context-menus.git`

## Team

  * [Metin Can Siper](https://github.com/metincansiper), [Ugur Dogrusoz](https://github.com/ugurdogrusoz) of [i-Vis at Bilkent University](http://www.cs.bilkent.edu.tr/~ivis)
