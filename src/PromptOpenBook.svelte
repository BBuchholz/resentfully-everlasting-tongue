<script>
  
  import { getContext } from 'svelte';

  const { close } = getContext('simple-modal');

  import { getNotificationsContext } from 'svelte-notifications';
  const { addNotification } = getNotificationsContext();

  import { 
    currentBook,
    currentBookTitle,
    currentBookCount,
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

  function openTestBook() {

    let newBook = { title: 'Test ' + $currentBookCount };
    $currentBook = newBook;
    $currentBookCount = $currentBookCount + 1;
    
    notify('opened book: ' + $currentBookTitle);
  }
  
  function handleCloseClick(){

    openTestBook();
    close();
  }


</script>

<div class='daedalus-lab'>
  
    <div class="lab-item">
      <a 
        href="#ClosedPrompt"
        on:click={handleCloseClick}
      > 
        Close
      </a>
    </div>
  
</div>

<style>

.daedalus-lab {
  border: solid;
  border-radius: 10px;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}

.lab-item {
  margin: 10px;
  padding: 10px;
  border: thin solid;
  border-radius: 10px;
}

</style>