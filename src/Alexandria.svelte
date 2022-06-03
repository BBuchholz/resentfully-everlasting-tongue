<script>
  
  import { getContext } from 'svelte';

  const { close } = getContext('simple-modal');

  import { getNotificationsContext } from 'svelte-notifications';
  const { addNotification } = getNotificationsContext();

  function notify(textValue){
    addNotification({
      position: 'bottom-right',
      text: textValue,
      type: 'error',
      description: 'lorem ipsum',
      removeAfter: 3000,
      disableButtons: true,
      disableDescription: true
    });
  }

  function handleOpenBookClick(){
    
    notify('test');
  }

</script>

<div class='main'>

  <div class='citadel-shelf'>
    
      <div class="book">
        <a 
          href="#openBook"
          on:click={handleOpenBookClick}
        > 
          Open Book 
        </a>
      </div>
    
  </div>

  

</div>

<style>

.citadel-shelf {
  border: solid;
  border-radius: 10px;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}

.book {
  margin: 10px;
  padding: 10px;
  border: thin solid;
  border-radius: 10px;
}

</style>