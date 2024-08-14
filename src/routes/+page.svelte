<script>
	import Header from '../Header.svelte';
	import myjson from './music.json';

	function downloadFile(path, name) {
		const link = document.createElement('a');
		link.href = path;
		link.download = name;

		document.body.appendChild(link);
		link.click();

		document.body.removeChild(link);
	}
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
			<a class="download-btn" on:click={() => downloadFile(music.path, music.name)}>Download</a>
		</div>
	{/each}
</div>

<style>
	.music {
		margin: 5px;
	}

	.download-btn {
		font-weight: 600;
		cursor: pointer;
		color: #ca2c92;
	}

	.download-btn:hover {
		color: #ca2c93c9;
	}
</style>
