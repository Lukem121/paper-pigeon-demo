<script>
	import { Discord, Slack } from 'paper-pigeon';
	const send = new Discord("https://discordapp.com/api/webhooks/763031675361034260/Al45h0W9IbGDowO9kNzs0LtUGJWb-PQYzv_MbpqSSx_4YEERFoYhHzBIFAgsfKLd1gMD");
	const sendSlack = new Slack("https://hooks.slack.com/services/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");

	//Discords
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
	//Slack
	let textSlack = "";

	const handleNormalSlack = () => {
		if(textSlack != ""){
			sendSlack.message(textSlack);
		}
	}
	const handleSuccessSlack = () => {
		if(textSlack != ""){
			sendSlack.success(textSlack);
		}
	}
	const handleErrorSlack = () => {
		if(textSlack != ""){
			sendSlack.error(textSlack);
		}
	}
</script>

<main>
	<h2>Discord</h2>
	<span>1. </span><a target="_blank" href="https://discord.gg/rP6RmNK">Join the Discord</a>
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
	<br>

	<hr>

	<br>
	<h2>Slack</h2>
	<span>1. </span><a target="_blank" href="https://rashek.slack.com/archives/C01BW8TMXE2">Join the Slack channels</a>
	<br>
	<br>
	<span>2. </span>
	<input bind:value={textSlack} type="text">
	<br>
	<br>
	<span>3. </span>
	<button on:click={handleNormalSlack} style="background: #007bff;" >Normal</button>
	<button on:click={handleSuccessSlack} style="background: #28a745;" >Success</button>
	<button on:click={handleErrorSlack} style="background: #dc3545;">Error</button>

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