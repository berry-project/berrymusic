<script>
	import Header from '../Header.svelte';
	import myjson from './music.json';
</script>

<div class="container">
	<Header />
	{#each myjson as music}
		<div class="music">
			<p>{music.name} <i>[{music.genre}]</i></p>
			<audio controls>
				<source src={music.path} type="audio/mpeg" />
				Your browser does not support the audio element.
			</audio>
			<p></p>
			<a class="download-btn" href={music.path} download={music.name}>Download</a>
		</div>
	{/each}
</div>

<style>
	.music {
		margin: 5px;
	}

	.download-btn {
		font-weight: 600;
		color: #ca2c92;
		text-decoration: none;
	}

	.download-btn:hover {
		color: #ca2c93c9;
	}
</style>
