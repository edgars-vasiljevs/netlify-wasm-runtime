<script>

    let text, output;

    async function upload() {

        const rawResponse = await fetch('https://dapper-cendol-cd648a.netlify.app/.netlify/functions/hello', {
            method: 'POST',
            headers: {
                'Accept': 'application/json',
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({a: 1, b: 'Textual content'})
        });

        output.innerHTML = rawResponse;
    }

</script>

<div style="padding: 30px">
    <div>
        <textarea bind:this={text} name="name" id="text" cols="150" rows="30"></textarea>
    </div>
    <div>
        <button on:click|preventDefault={upload}>Upload SVG string</button>
    </div>
    <div style="padding: 20px 0;" bind:this={output}>

    </div>
</div>