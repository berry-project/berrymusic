<script>

	import { page } from '$app/stores';

	import Header from '../Header.svelte';
</script>

<svelte:head>
	<title>404 Not Found</title>
</svelte:head>

<Header />

<div class="container">
	<h1>Oops! Something went wrong.</h1>
	<p>{$page.error.message}</p>
	<a href="/">Go back to the homepage</a>
</div>

<style>
    .container {
        margin: 5px;
    }
</style>