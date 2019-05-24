<script>
    let hobbies = [];
    let hobbyInput;
    
    function addHobby() {
        hobbies = [...hobbies, hobbyInput.value];
    
        fetch('https://svelte-http.firebaseio.com/skills.json', {
            method: 'POST',
            body: JSON.stringify(hobbies),
            headers: {
                'content-Type': 'application/json'
            }
        }).then(res => {
            if (!res.ok) {
                throw new Error('Failed!');
            }
            // ... 
        }).catch(err => {
            console.log(err);
        });
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
