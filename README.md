# safe-delete
[![it](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/matt-tro/ateco-sql/blob/master/README.md)
[![en](https://img.shields.io/badge/lang-it-green.svg)](https://github.com/matt-tro/ateco-sql/blob/master/README.it.md)

Bootstrap plugin for safe deletion with confirm prompt<br />
Check-out this fork by jqueryscript https://www.jqueryscript.net/lightbox/Double-Confirmation-Bootstrap-Safe-Delete.html that enhances this project

# Dependencies
Bootstrap 3.3.6
jQuery 1.9.1

# How to use
After integrating the script in your page, you can call the plugin from any element like this

```html
<button class="btn btn-danger btn-safe-delete" data-safe-delete-id="3536">DELETE ME</button>
```

```javascript
$('.btn-safe-delete').on('click', function(){
  var id = $(this).attr('data-safe-delete-id');
  $(this).safeDelete({
    yesCallback : function(){
      $.ajax({
          url: '/my/delete/url/' + id,
          type: 'DELETE'
      });
    }
  });
});
```

# Arguments
safe-delete allows you to customise some things

```javascript
var options = {
    popupTitle : "Type KILL IT WITH FIRE then click the button",
    yesCallback : function(){},
    noCallback : function(){},
    safeText : "KILL IT WITH FIRE",
    closeOnSelection : true,
    deleteButton : "DELETE",
    cancelButton : "NEVERMIND"            
};

$(element).safeDelete(options);
```

| Property             | Description                                                                                           |
| :------------------- | :---------------------------------------------------------------------------------------------------- |
| **popupTitle**       | will change the title of the popup                                                                    |
| **yesCallback**      | is the function to be executed when the deletion is confirmed                                         |
| **noCallback**       | is the function to be executed when the deletion is cancelled                                         |
| **safeText**         | is the text that the user is required to write in order to enable the delete button (case sensitive!) |
| **closeOnSelection** | default at true, lets you choose if you want the popup to close after the selection or not            |
| **deleteButton**     | makes you choose the text to put inside the delete button                                             |
| **cancelButton**     | makes you choose the text to put inside the cancel button                                             |

# Mantainers
- Marco Bimbati
- Mattia Trombon
- Francesca Reale
