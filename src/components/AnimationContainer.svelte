<script>
	let titre = "/"
	let explications = "/"
	let hidden = true


	let boutons = [
		{
			"nom": "Règlement",
			"titre": "Règlement",
			"explications": "Texte explicatif",
			"balle": true
		}, 
		{
			"nom": "FAQ",
			"titre": "FAQ",
			"explications": "Texte explicatif",
			"balle": true
		}, 
		{
			"nom": "Contact",
			"titre": "Contact",
			"explications": "Texte explicatif",
			"balle": true
		}, 
		{
			"nom": "Archives",
			"titre": "Archives",
			"explications": "Texte explicatif",
			"balle": true
		}, 
	]

	function menu(index){
		hidden = false
		let current = boutons[index]
		titre = current.titre
		explications = current.explications
		
		for(let i in boutons){
			boutons[i].balle = true
			boutons[i] = boutons[i]
		}

		current.balle = false
		boutons[index] = current

		setTimeout(() =>{
			current.balle = true
			boutons[index] = current
		}, 300)
	}
</script>

<style>
	div{
		border: 1px solid black;
		width: 100%;
	}
	button{
		width: 125px;
		margin: 15px;
	}
	img{
		position:absolute;
		top: 0;
		right: -100px;
	}
	img.balle{
		transform: rotate(180deg);
		right: -150px;
		transition: all 0.3s ease;
	}
	.hidden{
		display: none;
	}
	#cadrebouton{
		display:flex;
		flex-direction: row;
	}
	#container{
		display : flex;
		flex-direction: column;
		max-width: 155px;
		margin-right: 110px;
	}
	.boutoncontainer{
		display: flex;
		justify-content: space-between;
		position:relative;
	}
	.hiddenballe{
		opacity: 0;
		right:-100px!important;
		transition: opacity 0s 0s !important;
	}
</style>

<div id="cadrebouton">
	<div id="container">
		{#each boutons as x, index}
			<div class="boutoncontainer">
					<button on:click={() => {  menu(index) }}>{x.nom}</button>
					<img src="/images/revolver.png" alt="nope" width="95px">
					<img class="balle" class:hiddenballe={x.balle} src="/images/balle.png" alt="nope" width="50px">
			</div>
		{/each}
	</div>
	<div class:hidden>
		<h4>
			{titre}
		</h4>
		<p>
			{explications}
		</p>	
	</div>
</div>