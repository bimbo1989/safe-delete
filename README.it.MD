# ateco-sql
[![en](https://img.shields.io/badge/lang-en-red.svg)](https://github.com/bimbo1989/safe-delete/blob/master/README.md)

Plugin Bootstrap per l'eliminazione sicura con richiesta di conferma <br/>
Dai un'occhiata a questo fork di jqueryscript https://www.jqueryscript.net/lightbox/Double-Confirmation-Bootstrap-Safe-Delete.html che migliora questo progetto

# Dipendenze
Bootstrap 3.3.6
jQuery 1.9.1

# Come utilizzarlo
Dopo aver integrato lo script nella tua pagina, puoi chiamare il plugin da qualsiasi elemento come questo

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

# Argomenti
safe-delete ti permette di personalizzare alcune cose

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
| **popupTitle**       | cambierà il titolo del popup                                                                          |
| **yesCallback**      | funzione che viene eseguita quando la cancellazione è confermata                                      |
| **noCallback**       | funzione che viene eseguita quando la cancellazione è annullata                                       |
| **safeText**         | è il testo che viene richiesto per abilitare il bottone di conferma cancellazione (case sensitive!)   |
| **closeOnSelection** | default a true, lascia scegliere se chiudere il popup dopo la selezione o meno                        |
| **deleteButton**     | ti fa scegliere il testo da inserire all'interno del pulsante di eliminazione                         |
| **cancelButton**     | ti fa scegliere il testo da inserire all'interno del pulsante di annullamento                         |

# Gestito da
- Marco Bimbati
- Mattia Trombon
- Francesca Reale
