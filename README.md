# safe-delete
Bootstrap plugin for safe deletion with confirm prompt

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

**popupTitle** will change the title of the popup <br />
**yesCallback** is the function to be executed when the deletion is confirmed <br />
**noCallback** is the function to be executed when the deletion is cancelled <br />
**safeText** is the text that the user is required to write in order to enable the delete button (case sensitive!) <br />
**closeOnSelection**, default at true, lets you choose if you want the popup to close after the selection or not <br />
**deleteButton** makes you choose the text to put inside the delete button <br />
**cancelButton** makes you choose the text to put inside the cancel button <br />
