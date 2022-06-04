<script>
  
  import { getContext } from 'svelte';

  const { close } = getContext('simple-modal');

  import { getNotificationsContext } from 'svelte-notifications';
  const { addNotification } = getNotificationsContext();

  import { 
    currentBook,
    currentBookTitle,
  } from './stores.js';

  function notify(textValue){
    addNotification({
      position: 'top-right',
      text: textValue,
      type: 'error',
      description: 'lorem ipsum',
      removeAfter: 3000,
      disableButtons: true,
      disableDescription: true
    });
  }

  let count = 0;

  function handleOpenBookClick(){
    
    let newBook = { title: 'Test ' + count };
    $currentBook =newBook 
    count++;
    
    notify('opened book: ' + $currentBookTitle);
  }
</script>

<div class="open-book-option">
  
  <a 
    href="#openBook"
    on:click={handleOpenBookClick}
  > 
    Open Book 
  </a>
</div>

<style>


.open-book-option {
  margin: 10px;
  padding: 10px;
  border: thin solid;
  border-radius: 10px;
}


</style>