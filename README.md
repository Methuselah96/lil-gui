# lil-gui

Makes a floating panel with controllers for web demos.

```js
import GUI from 'lil-gui';

const myObject = {
    myBoolean: true,
    myFunction: function() { ... },
    myString: 'lil-gui',
    myNumber: 1
};

const gui = new GUI();

gui.add( myObject, 'myBoolean' ); // checkbox
gui.add( myObject, 'myFunction' ); // button
gui.add( myObject, 'myString' ); // text field
gui.add( myObject, 'myNumber', 0, 1 ); // slider

// dropdowns
gui.add( myObject, 'myNumber', [ 0, 1, 2 ] );
gui.add( myObject, 'myNumber', { Label1: 0, Label2: 1, Label3: 2 } );

// chainable methods
gui.add( myObject, 'myProperty' )
    .name( 'Custom Name' )
    .onChange( value => {
        
    } );

const colorFormats = {
    string: '#ffffff',
    int: 0xffffff,
    object: { r: 1, g: 1, b: 1 },
    array: [ 1, 1, 1 ]
};

// colors
gui.addColor( colorFormats, 'string' );

// folders
const folder = gui.addFolder( 'Title' );
folder.add( myObject, 'myProperty' );
```