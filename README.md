# quicksettings
QuickSettings is a JavaScript library for making a quick settings panel to control code parameters.

HTML UI controls are created within a QuickSettings panel on your page. Create the panel with:

    var settings = QuickSettings.create(x, y, panelTitle);

Now you can add controls to the panel. Supported controls are:

    settings.addRange(title, min, max, value, step, callback);  // creates a range slider
    settings.addColor(title, color, callback);                  // creates a color input
    settings.addBoolean(title, value, callback);                // creates a checkbox
    settings.addText(title, text, callback);                    // creates an input text field
    settings.addButton(title, callback);                        // creates a button
    settings.addInfo(title, text);                              // creates informational text

For range, color, boolean and text, the callback will pass the current value of the control. For the button, it passes a reference to the button itself.

You can also query the value of controls at any time with:

    settings.getRangeValue(title);
    settings.getBooleanValue(title);
    settings.getColorValue(title);
    settings.getText(title);

The panel is draggable and collapsible/expandable by a double click on the title bar by default. The following methods affect this behavior:

    settings.setDraggable(bool);
    settings.setCollaspible(bool);
    settings.collapse();
    settings.expand();
    settings.toggleCollapsed():

You can show and hide the panel with the following:

    settings.show();
    settings.hide();
    settings.toggleVisibility();
  
Or, you can set a keyboard key that will show and hide the panel when pressed:

    settings.setKey(char);
  
You can set the position of the panel with:

    settings.setPosition(x, y);

By default, the panel will be 200px wide and grow in height to fit its content. You can set an explicit size with:

    settings.setSize(w, h);

Styles are in quicksettings.css which must be included.

Add the library in a script tag, or via require.js.