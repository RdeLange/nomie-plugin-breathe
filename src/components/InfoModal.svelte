<script>
    import { createEventDispatcher } from 'svelte';
    import {
      Button,
      ComposedModal,
      ModalHeader,
      ModalBody,
      ModalFooter,
    } from "carbon-components-svelte";
   
   let open=true;
   const dispatch = createEventDispatcher();

   function exitInfo(){
        dispatch("exitinfo");
        open = false;
    }
</script>


<ComposedModal bind:open on:close={() => { exitInfo();}} on:submit={() => { exitInfo();}} >
    <ModalHeader label="Nomie Breathe" title="General Information" />
    <ModalBody>
      <h1 style="text-align:center">🫁</h1>
      <h2 style="text-align:center">Nomie Breathe</h2>
      <h5 style="text-align:center">General Information</h5>
      <hr><br>
     
     <h4>Additional Log Entry Input:</h4>
     
    </ModalBody>
    <ModalFooter
      primaryButtonText="Update & Exit"
      primaryButtonDisabled={false} 
      secondaryButtons={[{ text: "Cancel" }]}
      on:click:button--secondary={({ detail }) => {
        if (detail.text === "Cancel") exitInfo(); 
      }}
    />
  </ComposedModal>

  <style>
     h2 {
        margin: 0;
        padding: 0;
		font-size: 2.5em;
		font-weight: 400;
	}

  h6 {
        margin: 0;
        padding: 0;
		font-size: 0.8em;
		font-weight: 300;
	}

  p {
        height: 45px;
        line-height: 45px;
        text-align: center;
      }


  </style>
