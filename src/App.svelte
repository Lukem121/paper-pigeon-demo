<script>
	import { Discord } from 'paper-pigeon';
	const send = new Discord(WEBHOOK_URL);

	let text = "";

	const handleNormal = () => {
		if(text != ""){
			send.message(text);
		}
	}
	const handleSuccess = () => {
		if(text != ""){
			send.success(text);
		}
	}
	const handleError = () => {
		if(text != ""){
			send.error(text);
		}
	}
</script>

<main>
	<span>1. </span><a href="https://discord.gg/rP6RmNK">Join the discord</a>
	<br>
	<br>
	<span>2. </span>
	<input bind:value={text} type="text">
	<br>
	<br>
	<span>3. </span>
	<button on:click={handleNormal} style="background: #007bff;" >Normal</button>
	<button on:click={handleSuccess} style="background: #28a745;" >Success</button>
	<button on:click={handleError} style="background: #dc3545;">Error</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	button{
		cursor: pointer;
		color: white;
		border-radius: .25rem;
		border: 1px solid transparent;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>