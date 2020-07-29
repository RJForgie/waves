<script lang="ts">
	export let name: string;
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

	<div class="ocean">
		<div class="wave"></div>
		<div class="wave"></div>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 0;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	.ocean { 
		height: 5%;
		width:100%;
		position:absolute;
		bottom:0;
		left:0;
		background: #015871;
	}

	.wave {
		background: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/85486/wave.svg) repeat-x; 
		position: absolute;
		top: -198px;
		width: 6400px;
		height: 198px;
		animation: wave 7s cubic-bezier( 0.36, 0.45, 0.63, 0.53) infinite;
		transform: translate3d(0, 0, 0);
	}

	.wave:nth-of-type(2) {
		top: -175px;
		animation: wave 7s cubic-bezier( 0.36, 0.45, 0.63, 0.53) -.125s infinite, swell 7s ease -1.25s infinite;
		opacity: 1;
	}

	@keyframes wave {
		0% {
			margin-left: 0;
		}
		100% {
			margin-left: -1600px;
		}
	}

	@keyframes swell {
		0%, 100% {
			transform: translate3d(0,-25px,0);
		}
		50% {
			transform: translate3d(0,5px,0);
		}
	}
</style>