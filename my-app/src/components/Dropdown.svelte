<!-- Dropdown.svelte -->
<script>
    let selectedOption = "";
    
    function handleChange(event) {
      selectedOption = event.target.value;
    }
  </script>
  
  <main>
    <h1>Jobs</h1>
    
    <label for="dropdown">Select an option:</label>
    <select id="dropdown" on:change={handleChange}>
      <option value="">Select an option</option>
      <option value="option1">SOFTWARE DEVELOPER</option>
      <option value="option2">SOFTWARE ASSISSTANT</option>
      <option value="option3">SOFTWARE ENGINEER</option>
    </select>
    
    {#if selectedOption}
      <p>You selected: {selectedOption}</p>
    {/if}
  </main>
  