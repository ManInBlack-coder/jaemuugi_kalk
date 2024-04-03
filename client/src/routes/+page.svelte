<script lang="ts">

    let discount = {
        1000: 3,
        5000: 5,
        7000: 7,
        10000: 10,
        50000: 15
    };
    let nimi = '';
    let hind = 0;
    let tax = 6.85;
    let total = '';

    const calculate = (e: Event) => {
        e.preventDefault();
        let temp = hind * (1 + tax / 100);
        for(const [key, value] of Object.entries(discount)){
            if(temp >= parseInt(key)){
                total = (temp * (1 - value / 100)).toFixed(2);
                return;
            }
        }
        total = temp.toFixed(2);
        
    }

    const handleSubmit = (e: Event) =>{
        e.preventDefault();
        nimi = (e.target as HTMLFormElement).nimi.value;
        calculate(e);
    }

</script>

<div class="container">
    <h1>Jaemüügi kalkulaator!!!</h1>
    
    <div class="calculator">
        <form on:submit={handleSubmit}>
            <div class="field">
                <label for="nimi">Nimi</label>
                <input type="text" name="nimi">
            </div>
            <div class="field">
                <label for="hind">Hind</label>
                <input type="text" name="hind" bind:value={hind}>
            </div>
            <div class="field">
                <label for="state">Osariik</label>
                <select name="state" bind:value={tax}>
                    <option value={6.85}>UT</option>
                    <option value={8.00}>NV</option>
                    <option value={6.25}>TX</option>
                    <option value={4.00}>AL</option>
                    <option value={8.25}>CA</option>
                </select>
            </div>
            <div class="field submit">
                <button type="submit">Arvuta</button>
            </div>
        </form>
    </div>
    {#if total && nimi}
        <h2>{nimi} hind: {total}</h2>
    {/if}
</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Reddit+Mono:wght@200..900&display=swap');
    div{
        font-family: 'Reddit Mono', monospace;
    }
    .container{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
    }
    .calculator{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        border: 2px solid black;
        padding: 20px;
        border-radius: 10px;
    }
    .field{
        padding: 10px;
    }
    .submit{
        display: flex;
        justify-content: center;
    }
    .submit button{
        padding: 10px 20px;
        background-color: cornflowerblue;
        color: white;
        border: none;
        border-radius: 5px;
        transition: all 0.2s;
    }
    .submit button:hover{
        transform: translate(-2px, -2px);
        box-shadow: 2px 2px 2px rgba(0,0,0,0.2);
        cursor: pointer;
    }
    .submit button:active{
        transform: translate(0, 0);
        box-shadow: none;
    }
    .field input{
        padding: 5px;
    }
</style>