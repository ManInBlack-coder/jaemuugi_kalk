<script>

</script>

<div class="container">
    <h1>Jaemüügi kalkulaator!!!</h1>
    
    <div class="calculator">
        <form>
            <div class="field">
                <label for="nimi">Nimi</label>
                <input type="text" name="nimi">
            </div>
            <div class="field">
                <label for="hind">Hind</label>
                <input type="text" name="hind">
            </div>
            <div class="field">
                <label for="state">Osariik</label>
                <select name="state">
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