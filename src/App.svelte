<script>
	let col = 'aquamarine';
	function change(){
		if(col === 'aquamarine'){
			col = 'orangered';
		}
		else{
			col = 'aquamarine';
		}
	}
</script>

<main>
	<section class="glass">
		<div class="dash">
			<div class="user">
				<input bind:value={col} type="text">
				<input bind:value={col} type="color">
				<button class='butt' on:click={change} style="--aqua:{col}">Neon</button>
			</div>
		</div>
	</section>
</main>

<style>
	*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
:root{
    --sky1:rgb(99, 255, 237);
    --sky2:skyblue;
    --nky1:rgb(255, 161, 53);
    --nky2:black;
	--aqua:aquamarine;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
main{
    min-height: 100vh;
    background: linear-gradient(to right top, var(--sky1),var(--sky2) );
    display: flex;
    align-items: center;
    justify-content: center;
}
.glass{
  background-color: aliceblue;
  height: 80vh;
  width: 60%;
  border-radius: 2rem;
}

.dash{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
}
.user{
    background-color: black;
    height: 100%;
    width:100%;
    border-radius:1.5rem;
    display: flex;
	flex-direction: column;
    justify-content:center ;
    align-items: center;
}

.butt{
    font-size: 2rem;
    background-color: transparent;
    color: var(--aqua);
    border:solid .125em var(--aqua);
    padding:.3em;
    border-radius:15%;
    position: relative;
    cursor: pointer;
}
.butt:hover.butt::before{
    content: '';
    position: absolute;
    background-color: var(--aqua);
    top: 120%;
    width: 100%;
    height: 100%;
    transform: perspective(1em) rotateX(30deg) scale(1, .5);
    filter: blur(1em);
    pointer-events: none;
}
.butt:hover{
    font-size: 2rem;
    background-color: transparent;
    color: var(--aqua);
    border:solid .125em var(--aqua);
    padding:.3em;
    border-radius:15%;
    text-shadow: 0 0 .25em var(--aqua);
    box-shadow: inset 0 0 .30em var(--aqua), 0 0 .30em var(--aqua);
    position: relative;
    cursor: pointer;
}
</style>