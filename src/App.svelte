<script>
    let hobbies = [];
    let hobbyInput;
    
    function addHobby() {
        hobbies = [...hobbies, hobbyInput.value]
    }
</script>

<label for="hobby">Skills</label>
<input type="text" id="hobby" bind:this={hobbyInput}>
<button on:click={addHobby}>Add Skills</button>

<ul>
{#each hobbies as hobby}
    <li>{hobby}</li>
{/each}
</ul>
