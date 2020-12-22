<script lang="ts">
	let loaded: string = "test";
	firebase.analytics();

	try {
		var app = firebase.app();
		var features = [
			"auth",
			"database",
			"firestore",
			"functions",
			"messaging",
			"storage",
			"analytics",
			"remoteConfig",
			"performance",
		].filter((feature) => typeof app[feature] === "function");
		loaded = `Firebase SDK loaded with ${features.join(", ")}`;
	} catch (e) {
		console.error(e);
		loaded = "Error loading the Firebase SDK, check the console.";
	}
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #286e97;
		font-weight: 100;
		font-size: 4em;
		text-transform: uppercase;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

<main>
	<h1>Hello World!</h1>
	<p>{loaded}</p>
</main>
