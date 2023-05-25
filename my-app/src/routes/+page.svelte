
<!-- src/routes/index.svelte -->
<script>
    import Dropdown from '../components/Dropdown.svelte';
  
    let title = 'NOTIFICATION';
  
    let selectedBatch = "";
    let isCheckboxChecked = false;
  
    function selectBatch(event) {
      selectedBatch = event.target.value;
    }
  
    function toggleCheckbox() {
      isCheckboxChecked = !isCheckboxChecked;
    }
  
    function saveDetails() {
      // Add logic to save the details
      
      // Show "SAVED" message
      alert("SAVED");
    }
  </script>
  
  <main>
    <h1>{title}</h1>
    <p>It is to notify the students about the jobs</p>
  
    <Dropdown id="jobName" label="Select a job name" />
  
    <select id="batch" on:change={selectBatch}>
      <option value="">Select a batch</option>
      <option value="batch1">Batch 1</option>
      <option value="batch2">Batch 2</option>
      <option value="batch3">Batch 3</option>
    </select>
  
    {#if selectedBatch}
      <p>Selected batch: {selectedBatch}</p>
      <a href="mailto:imca-221@scmsgroup.org?subject=JOB DRIVE">Send Email</a>
  
      <br />
  
      <label>
        <input type="checkbox" checked={isCheckboxChecked} on:change={toggleCheckbox} />
        I HAVE NOTIFIED  THE BATCHES
      </label>
  
      {#if isCheckboxChecked}
        <p>NOTIFIED!</p>
      {/if}
  
      <button on:click={saveDetails}>Save</button>
    {/if}
  </main>
  
  <style>
    main {
      text-align: center;
      margin: 20px auto;
    }
  </style>
  