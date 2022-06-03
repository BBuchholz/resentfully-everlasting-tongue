<script>

  import Modal from 'svelte-simple-modal';
  import Notifications from 'svelte-notifications';

  import { 
    modal,
    headerQuote,
  } from './stores.js';

  import MyriadNotification from './MyriadNotification.svelte';

  import Alexandria from './Alexandria.svelte';

</script>


<Notifications item={MyriadNotification}>

  <Modal show={$modal}>
    
    <main>

      <div class='header'>
        
        <p>
        
        {$headerQuote.content}
        
        </p>
        
        <p>

        - {$headerQuote.source}

        </p>
      
      </div>

      <Alexandria />

      <div class='footer'>
        
        a Temple Cathedral Tomb production

      </div>

    </main>

  </Modal>

</Notifications>

<style>

@import url('https://fonts.googleapis.com/css2?family=Averia+Serif+Libre:wght@300&display=swap');

.header, .footer {
  width: 80%;
  position: relative;
  height: auto;
  padding: 20px;
  margin: 20px;
}

.header {
  font-family: 'Averia Serif Libre', cursive;
  font-size: 18px;
  font-style: italic;
  line-height: 17px;

}

.footer {
  font-family: 'Averia Serif Libre', cursive;
  font-size: 18px;
  font-style: italic;
  line-height: 17px;
}

main {
  text-align: center;
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
}


</style>